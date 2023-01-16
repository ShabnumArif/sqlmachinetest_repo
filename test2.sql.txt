Table:1

machinetest=# insert into tbl_stock values(1, 'Mouse', 10, 500, 1);
INSERT 0 1
machinetest=# insert into tbl_stock values(2, 'Keyboard', 5, 450, 3);
INSERT 0 1
machinetest=# insert into tbl_stock values(3, 'Modem', 10, 1200, 2);
INSERT 0 1
machinetest=# insert into tbl_stock values(4, 'Memory', 100, 1500, 5);
INSERT 0 1
machinetest=# insert into tbl_stock values(5, 'Headphone', 50, 750, 4);
INSERT 0 1
machinetest=# insert into tbl_stock values(6, 'Memory', 2, 3500, 4);
INSERT 0 1
machinetest=# select * from tbl_stock;
 pk_int_stock_id | vchr_name | int_quantity | int_price | fk_int_supplier
-----------------+-----------+--------------+-----------+-----------------
               1 | Mouse     |           10 |       500 |               1
               2 | Keyboard  |            5 |       450 |               3
               3 | Modem     |           10 |      1200 |               2
               4 | Memory    |          100 |      1500 |               5
               5 | Headphone |           50 |       750 |               4
               6 | Memory    |            2 |      3500 |               4
(6 rows)






Table:2

machinetest=# update tbl_stock set int_price = 501.5 where pk_int_stock_id = 1;
UPDATE 1
machinetest=# update tbl_stock set int_price = 451.5 where pk_int_stock_id = 2;
UPDATE 1
machinetest=# update tbl_stock set int_price = 1201.5 where pk_int_stock_id = 3;
UPDATE 1
machinetest=# update tbl_stock set int_price = 1501.5 where pk_int_stock_id = 4;
UPDATE 1
machinetest=# update tbl_stock set int_price = 751.5 where pk_int_stock_id = 5;
UPDATE 1
machinetest=# update tbl_stock set int_price = 3501.5 where pk_int_stock_id = 6;
UPDATE 1
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


Table:3

machinetest=# select * from tbl_stock where int_price>1000;
 pk_int_stock_id | vchr_name | int_quantity | int_price | fk_int_supplier
-----------------+-----------+--------------+-----------+-----------------
               3 | Modem     |           10 |    1201.5 |               2
               4 | Memory    |          100 |    1501.5 |               5
               6 | Memory    |            2 |    3501.5 |               4
(3 rows)



Table:4

machinetest=# select  pk_int_stock_id, vchr_name, int_quantity, int_price, fk_int_supplier from tbl_stock order by vchr_name ASC;
 pk_int_stock_id | vchr_name | int_quantity | int_price | fk_int_supplier
-----------------+-----------+--------------+-----------+-----------------
               5 | Headphone |           50 |     751.5 |               4
               2 | Keyboard  |            5 |     451.5 |               3
               4 | Memory    |          100 |    1501.5 |               5
               6 | Memory    |            2 |    3501.5 |               4
               3 | Modem     |           10 |    1201.5 |               2
               1 | Mouse     |           10 |     501.5 |               1
(6 rows)



Table:5

machinetest=# select  pk_int_stock_id, vchr_name, int_quantity, int_price, fk_int_supplier from tbl_stock order by vchr_name ASC limit 3;
 pk_int_stock_id | vchr_name | int_quantity | int_price | fk_int_supplier
-----------------+-----------+--------------+-----------+-----------------
               5 | Headphone |           50 |     751.5 |               4
               2 | Keyboard  |            5 |     451.5 |               3
               4 | Memory    |          100 |    1501.5 |               5
(3 rows)



Table:6

machinetest=# select  pk_int_stock_id, vchr_name, int_quantity, int_price, fk_int_supplier from tbl_stock order by vchr_name desc limit 3;
 pk_int_stock_id | vchr_name | int_quantity | int_price | fk_int_supplier
-----------------+-----------+--------------+-----------+-----------------
               1 | Mouse     |           10 |     501.5 |               1
               3 | Modem     |           10 |    1201.5 |               2
               4 | Memory    |          100 |    1501.5 |               5
(3 rows)



Table:7

machinetest=# select  pk_int_stock_id, vchr_name, (int_quantity * int_price), fk_int_supplier from tbl_stock;
 pk_int_stock_id | vchr_name | ?column? | fk_int_supplier
-----------------+-----------+----------+-----------------
               1 | Mouse     |     5015 |               1
               2 | Keyboard  |   2257.5 |               3
               3 | Modem     |    12015 |               2
               4 | Memory    |   150150 |               5
               5 | Headphone |    37575 |               4
               6 | Memory    |     7003 |               4
(6 rows)




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


machinetest=# insert into tbl_dept values(1, 'Computer Science', 'CS');
INSERT 0 1
machinetest=# insert into tbl_dept values(2, 'Electronics', 'EC');
INSERT 0 1
machinetest=# insert into tbl_dept values(3, 'Commerce', 'CC');
INSERT 0 1
machinetest=# insert into tbl_dept values(4, 'Arts', 'AA');
INSERT 0 1
machinetest=# select * from tbl_dept;
 pk_int_dept_id |  vchr_dept_name  | vchr_dept_description
----------------+------------------+-----------------------
              1 | Computer Science | CS
              2 | Electronics      | EC
              3 | Commerce         | CC
              4 | Arts             | AA
(4 rows)

