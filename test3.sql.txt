Table:1

machinetest=# select * from tbl_stock;
 pk_int_stock_id | vchr_name | int_quantity | int_price | fk_int_supplier
-----------------+-----------+--------------+-----------+-----------------
               1 | Mouse     |           10 |     501.5 |               1
               2 | Keyboard  |            5 |     451.5 |               3
               3 | Modem     |           10 |    1201.5 |               2
               4 | Memory    |          100 |    1501.5 |               5
               5 | Headphone |           50 |     751.5 |               4
               6 | Memory    |            2 |    3501.5 |               4
(6 rows)


machinetest=# select SUM(int_price) from tbl_stock;
 sum
------
 7909
(1 row)



Table:2

machinetest=# select Count(vchr_name) AS total_products from tbl_stock;
 total_products
----------------
              6
(1 row)


Table:3

machinetest=# select UPPER(vchr_name), ROUND(int_price) from tbl_stock;
   upper   | round
-----------+-------
 MOUSE     |   502
 KEYBOARD  |   452
 MODEM     |  1202
 MEMORY    |  1502
 HEADPHONE |   752
 MEMORY    |  3502
(6 rows)


Table:4

machinetest=# select count(*) As vchr_name from tbl_stock;
 vchr_name
-----------
         5
(1 row)


Table:5

machinetest=# select max(int_price) as highest_price from tbl_stock;
 highest_price
---------------
        3501.5
(1 row)


Table:6

machinetest=# select * from tbl_enrollment;
 pk_int_enrollment_id | int_count | fk_int_class_id
----------------------+-----------+-----------------
                    1 |        40 |               1
                    2 |        25 |               2
                    3 |        10 |               3
                    4 |        12 |               4
                    5 |        60 |               2
                    6 |        14 |               6
                    7 |       200 |               7
(7 rows)


machinetest=# select SUM(int_count) from tbl_enrollment;
 sum
-----
 361
(1 row)


Table:7
machinetest=# select * from tbl_classes;
 pk_int_class_id | vchr_class_name | fk_int_dept_id
-----------------+-----------------+----------------
               1 | CS100           |              1
               2 | CS101           |              1
               3 | CS102           |              1
               4 | CS103           |              1
               5 | EC200           |              2
               6 | CC300           |              3
               7 | AT400           |              4
(7 rows)
machinetest=# select count(*) As vchr_class_name from tbl_classes;
 vchr_class_name
-----------------
               7
(1 row)




Table:8

machinetest=# delete from tbl_stock where fk_int_supplier = 5;
DELETE 1
machinetest=# select * from tbl_stock;
 pk_int_stock_id | vchr_name | int_quantity | int_price | fk_int_supplier
-----------------+-----------+--------------+-----------+-----------------
               1 | Mouse     |           10 |     501.5 |               1
               2 | Keyboard  |            5 |     451.5 |               3
               3 | Modem     |           10 |    1201.5 |               2
               5 | Headphone |           50 |     751.5 |               4
               6 | Memory    |            2 |    3501.5 |               4
(5 rows)



Table:9
machinetest=# select CONCAT(vchr_name,int_price) from tbl_stock;
     concat
----------------
 Mouse501.5
 Keyboard451.5
 Modem1201.5
 Memory1501.5
 Headphone751.5
 Memory3501.5
(6 rows)



Table:10

machinetest=# select name, course from tbl_student INNER JOIN tbl_grade ON tbl_student.roll_no = tbl_grade.roll_no where grade='A'
machinetest-# ;
  name   | course
---------+--------
 Akhil   | c
 Maya    | Java
 Maya    | PHP
 Paul    | Java
 Sandeep | PHP
(5 rows)


Table:11

machinetest=# select name, course from tbl_student INNER JOIN tbl_grade ON tbl_student.roll_no = tbl_grade.roll_no where grade='B';
 name  | course
-------+--------
 Akhil | Java
 Maya  | C
 Anoop | Java
 Paul  | C
(4 rows)




machinetest=# create table tbl_student(Enrl_no int, Roll_no int, Name varchar(20), City varchar(20), Mobile bigint, Dob date);
CREATE TABLE
machinetest=# insert into tbl_student values(11, 2, 'Akhil', 'Delhi', 98756579, '12-01-1986');
INSERT 0 1
machinetest=# insert into tbl_student values(6, 4, 'Maya', 'Bangalore', 98734534, '12-11-1987');
INSERT 0 1
machinetest=# insert into tbl_student values(1, 8, 'Anoop', 'Bangalore', 93456535, '22-12-1990');
INSERT 0 1
machinetest=# insert into tbl_student values(20, 1, 'Paul', 'Cochin', 96754555, '13-03-1991');
INSERT 0 1
machinetest=# insert into tbl_student values(3, 5, 'Sandeep', 'Delhi', 84865644, '14-06-1993');
INSERT 0 1
machinetest=# select * from tbl_student;
 enrl_no | roll_no |  name   |   city    |  mobile  |    dob
---------+---------+---------+-----------+----------+------------
      11 |       2 | Akhil   | Delhi     | 98756579 | 1986-01-12
       6 |       4 | Maya    | Bangalore | 98734534 | 1987-11-12
       1 |       8 | Anoop   | Bangalore | 93456535 | 1990-12-22
      20 |       1 | Paul    | Cochin    | 96754555 | 1991-03-13
       3 |       5 | Sandeep | Delhi     | 84865644 | 1993-06-14
(5 rows)


machinetest=# create table tbl_grade (Roll_no int, Course varchar(20), grade varchar(5));
CREATE TABLE
machinetest=# insert into tbl_grade values(2,'c','A');
INSERT 0 1
machinetest=# insert into tbl_grade values(2,'Java','B');
INSERT 0 1
machinetest=# insert into tbl_grade values(1,'C','B');
INSERT 0 1
machinetest=# insert into tbl_grade values(1,'Java','A');
INSERT 0 1
machinetest=# insert into tbl_grade values(4,'PHP','A');
INSERT 0 1
machinetest=# insert into tbl_grade values(4,'Java','A');
INSERT 0 1
machinetest=# insert into tbl_grade values(4,'C','B');
INSERT 0 1
machinetest=# insert into tbl_grade values(8,'Java','B');
INSERT 0 1
machinetest=# insert into tbl_grade values(5,'PHP','A');
INSERT 0 1
machinetest=# insert into tbl_grade values(5,'Java','D');
INSERT 0 1
machinetest=# select * from tbl_grade;
 roll_no | course | grade
---------+--------+-------
       2 | c      | A
       2 | Java   | B
       1 | C      | B
       1 | Java   | A
       4 | PHP    | A
       4 | Java   | A
       4 | C      | B
       8 | Java   | B
       5 | PHP    | A
       5 | Java   | D
(10 rows)

machinetest=# select name, course from tbl_student INNER JOIN tbl_grade ON tbl_student.roll_no = tbl_grade.roll_no;
  name   | course
---------+--------
 Akhil   | c
 Akhil   | Java
 Paul    | C
 Paul    | Java
 Maya    | PHP
 Maya    | Java
 Maya    | C
 Anoop   | Java
 Sandeep | PHP
 Sandeep | Java
(10 rows)



Table:13

machinetest=# select name, city from tbl_student where city like '%e';
 name  |   city
-------+-----------
 Maya  | Bangalore
 Anoop | Bangalore
(2 rows)



Table:14

machinetest=# select name from tbl_student where name like 'A%';
 name
-------
 Akhil
 Anoop
(2 rows)

