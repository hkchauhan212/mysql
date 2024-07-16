Microsoft Windows [Version 10.0.22631.3880]
(c) Microsoft Corporation. All rights reserved.

C:\xampp\mysql\bin>

C:\xampp\mysql\bin>mysql -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 8
Server version: 10.4.32-MariaDB mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| hms                |
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| radhe              |
| student            |
| test               |
+--------------------+
8 rows in set (0.006 sec)

MariaDB [(none)]> use radhe;
Database changed
MariaDB [radhe]> show tables;
+-----------------+
| Tables_in_radhe |
+-----------------+
| hari            |
| namo            |
| registration    |
| studef          |
| students        |
| stunull         |
+-----------------+
6 rows in set (0.000 sec)

MariaDB [radhe]> desc hari;
+-----------+-------------+------+-----+---------+-------+
| Field     | Type        | Null | Key | Default | Extra |
+-----------+-------------+------+-----+---------+-------+
| user_id   | int(5)      | YES  |     | NULL    |       |
| name      | varchar(55) | YES  |     | NULL    |       |
| mo_no     | int(12)     | YES  |     | NULL    |       |
| state     | varchar(25) | YES  |     | NULL    |       |
| dis       | varchar(25) | YES  |     | NULL    |       |
| vill_name | varchar(30) | YES  |     | NULL    |       |
+-----------+-------------+------+-----+---------+-------+
6 rows in set (0.005 sec)

MariaDB [radhe]> desc namo;
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| no          | int(3)      | NO   |     | NULL    |       |
| first_name  | varchar(25) | NO   |     | NULL    |       |
| middle_name | varchar(25) | NO   |     | NULL    |       |
| last_name   | varchar(25) | NO   |     | NULL    |       |
| ssc         | int(4)      | NO   |     | NULL    |       |
| hsc         | int(4)      | NO   |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
6 rows in set (0.003 sec)

MariaDB [radhe]> create table smtjj (no int not null, name varchar(55) not null , collage_type varchar (15), mo_no int not null, father_no int not null, pay_fees);
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near ')' at line 1
MariaDB [radhe]> create table smtjj (no int not null, name varchar(55) not null , collage_type varchar (15), mo_no int not null, father_no int not null, pay_fees int not null);
Query OK, 0 rows affected (0.009 sec)

MariaDB [radhe]> desc smtjj;
+--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| no           | int(11)     | NO   |     | NULL    |       |
| name         | varchar(55) | NO   |     | NULL    |       |
| collage_type | varchar(15) | YES  |     | NULL    |       |
| mo_no        | int(11)     | NO   |     | NULL    |       |
| father_no    | int(11)     | NO   |     | NULL    |       |
| pay_fees     | int(11)     | NO   |     | NULL    |       |
+--------------+-------------+------+-----+---------+-------+
6 rows in set (0.002 sec)

MariaDB [radhe]> insert into smtjj values ('', 'chauhan harikrushan k', 'b.c.a', 7435088505, 9879184919, 25000);
Query OK, 1 row affected, 3 warnings (0.006 sec)

MariaDB [radhe]> select * from smtjj;
+----+-----------------------+--------------+------------+------------+----------+
| no | name                  | collage_type | mo_no      | father_no  | pay_fees |
+----+-----------------------+--------------+------------+------------+----------+
|  0 | chauhan harikrushan k | b.c.a        | 2147483647 | 2147483647 |    25000 |
+----+-----------------------+--------------+------------+------------+----------+
1 row in set (0.001 sec)

MariaDB [radhe]> insert into smtjj values ('', 'mori anil r', 'b.c.a', 6355277877, 123456780, 25000);
Query OK, 1 row affected, 2 warnings (0.001 sec)

MariaDB [radhe]> insert into smtjj values ('', 'kanjariya parvin b', 'b.c.a', 6355291069, 123456780, 25000);
Query OK, 1 row affected, 2 warnings (0.001 sec)

MariaDB [radhe]> select * from smtjj;
+----+-----------------------+--------------+------------+------------+----------+
| no | name                  | collage_type | mo_no      | father_no  | pay_fees |
+----+-----------------------+--------------+------------+------------+----------+
|  0 | chauhan harikrushan k | b.c.a        | 2147483647 | 2147483647 |    25000 |
|  0 | mori anil r           | b.c.a        | 2147483647 |  123456780 |    25000 |
|  0 | kanjariya parvin b    | b.c.a        | 2147483647 |  123456780 |    25000 |
+----+-----------------------+--------------+------------+------------+----------+
3 rows in set (0.000 sec)

MariaDB [radhe]> create table smtjj (no int not null, name varchar(55) not null , collage_type varchar (15), mo_no int not null, father_no int not null, pay_fees int not null default 000);
ERROR 1050 (42S01): Table 'smtjj' already exists
MariaDB [radhe]> create table smtjj (no int not null, name varchar(55) not null , collage_type varchar (15), mo_no int not null, father_no int not null, pay_fees int not null default '000');
ERROR 1050 (42S01): Table 'smtjj' already exists
MariaDB [radhe]> create table smtjj2 (no int not null, name varchar(55) not null , collage_type varchar (15), mo_no int not null, father_no int not null, pa
y_fees int not null default '000');
Query OK, 0 rows affected (0.006 sec)

MariaDB [radhe]> dessc smtjj2
    -> ;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'dessc smtjj2' at line 1
MariaDB [radhe]> show table smtjj2;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'smtjj2' at line 1
MariaDB [radhe]> desc smtjj2;
+--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| no           | int(11)     | NO   |     | NULL    |       |
| name         | varchar(55) | NO   |     | NULL    |       |
| collage_type | varchar(15) | YES  |     | NULL    |       |
| mo_no        | int(11)     | NO   |     | NULL    |       |
| father_no    | int(11)     | NO   |     | NULL    |       |
| pay_fees     | int(11)     | NO   |     | 0       |       |
+--------------+-------------+------+-----+---------+-------+
6 rows in set (0.002 sec)

MariaDB [radhe]> alter table smtjj2 add father_name varchar(30) not null default 'unname';
Query OK, 0 rows affected (0.005 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [radhe]> desc smtjj2;
+--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| no           | int(11)     | NO   |     | NULL    |       |
| name         | varchar(55) | NO   |     | NULL    |       |
| collage_type | varchar(15) | YES  |     | NULL    |       |
| mo_no        | int(11)     | NO   |     | NULL    |       |
| father_no    | int(11)     | NO   |     | NULL    |       |
| pay_fees     | int(11)     | NO   |     | 0       |       |
| father_name  | varchar(30) | NO   |     | unname  |       |
+--------------+-------------+------+-----+---------+-------+
7 rows in set (0.002 sec)

MariaDB [radhe]> alter table smtjj2 add fat varchar(30) not null;
Query OK, 0 rows affected (0.003 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [radhe]> desc smtjj2;
+--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| no           | int(11)     | NO   |     | NULL    |       |
| name         | varchar(55) | NO   |     | NULL    |       |
| collage_type | varchar(15) | YES  |     | NULL    |       |
| mo_no        | int(11)     | NO   |     | NULL    |       |
| father_no    | int(11)     | NO   |     | NULL    |       |
| pay_fees     | int(11)     | NO   |     | 0       |       |
| father_name  | varchar(30) | NO   |     | unname  |       |
| fat          | varchar(30) | NO   |     | NULL    |       |
+--------------+-------------+------+-----+---------+-------+
8 rows in set (0.002 sec)

MariaDB [radhe]> alter table smtjj2 drop fat ;
Query OK, 0 rows affected (0.004 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [radhe]> desc smtjj2;
+--------------+-------------+------+-----+---------+-------+
| Field        | Type        | Null | Key | Default | Extra |
+--------------+-------------+------+-----+---------+-------+
| no           | int(11)     | NO   |     | NULL    |       |
| name         | varchar(55) | NO   |     | NULL    |       |
| collage_type | varchar(15) | YES  |     | NULL    |       |
| mo_no        | int(11)     | NO   |     | NULL    |       |
| father_no    | int(11)     | NO   |     | NULL    |       |
| pay_fees     | int(11)     | NO   |     | 0       |       |
| father_name  | varchar(30) | NO   |     | unname  |       |
+--------------+-------------+------+-----+---------+-------+
7 rows in set (0.002 sec)

MariaDB [radhe]> show tables;
+-----------------+
| Tables_in_radhe |
+-----------------+
| hari            |
| namo            |
| registration    |
| smtjj           |
| smtjj2          |
| studef          |
| students        |
| stunull         |
+-----------------+
8 rows in set (0.000 sec)

MariaDB [radhe]> create table kfmskdfm (no int , name varchar (527));
Query OK, 0 rows affected (0.005 sec)

MariaDB [radhe]> desc kfmskdfm;
+-------+--------------+------+-----+---------+-------+
| Field | Type         | Null | Key | Default | Extra |
+-------+--------------+------+-----+---------+-------+
| no    | int(11)      | YES  |     | NULL    |       |
| name  | varchar(527) | YES  |     | NULL    |       |
+-------+--------------+------+-----+---------+-------+
2 rows in set (0.002 sec)

MariaDB [radhe]> drop table kfmskdfm;
Query OK, 0 rows affected (0.005 sec)

MariaDB [radhe]> show tables;
+-----------------+
| Tables_in_radhe |
+-----------------+
| hari            |
| namo            |
| registration    |
| smtjj           |
| smtjj2          |
| studef          |
| students        |
| stunull         |
+-----------------+
8 rows in set (0.000 sec)

MariaDB [radhe]> desc smtjj2;Ctrl-C -- exit!
Bye

C:\xampp\mysql\bin>
