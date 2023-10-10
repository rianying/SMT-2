rian@Rian Applications % /Applications/XAMPP/xamppfiles/bin/mysql -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 15
Server version: 10.4.21-MariaDB Source distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> create database 19225003_bab3a
    -> ;
Query OK, 1 row affected (0.004 sec)

MariaDB [(none)]> create database 19225003_bab3b;
Query OK, 1 row affected (0.001 sec)

MariaDB [(none)]> show databases;
```
+--------------------+
| Database           |
+--------------------+
| 19225003_bab3a     |
| 19225003_bab3b     |
| db_19225003        |
| db_latihan1        |
| db_les_private     |
| information_schema |
| komik_coba1        |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
11 rows in set (0.004 sec)
```

MariaDB [(none)]> use 19225003_bab3a;
Database changed

MariaDB [19225003_bab3a]> CREATE TABLE pedagang (
    ->     id_pedagang CHAR(5) NOT NULL PRIMARY KEY, 
    ->     nama_pedagang VARCHAR(35) NOT NULL, 
    ->     jns_kelamin VARCHAR(10) NOT NULL, 
    ->     alamat VARCHAR(50) NOT NULL, 
    ->     no_telp VARCHAR(18) NOT NULL, 
    ->     tgl_lahir DATE NOT NULL
    -> );
Query OK, 0 rows affected (0.017 sec)

MariaDB [19225003_bab3a]> create table barang (id_barang char(5) not null primary key, nama_barang varchar(35) not null, ukuran varchar(10) not null, warna varchar(15) not null);
Query OK, 0 rows affected (0.017 sec)

MariaDB [19225003_bab3a]> describe pedagang;
```
+---------------+-------------+------+-----+---------+-------+
| Field         | Type        | Null | Key | Default | Extra |
+---------------+-------------+------+-----+---------+-------+
| id_pedagang   | char(5)     | NO   | PRI | NULL    |       |
| nama_pedagang | varchar(35) | NO   |     | NULL    |       |
| jns_kelamin   | varchar(10) | NO   |     | NULL    |       |
| alamat        | varchar(50) | NO   |     | NULL    |       |
| no_telp       | varchar(18) | NO   |     | NULL    |       |
| tgl_lahir     | date        | NO   |     | NULL    |       |
+---------------+-------------+------+-----+---------+-------+
6 rows in set (0.007 sec)
```

MariaDB [19225003_bab3a]> describe barang;
```
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| id_barang   | char(5)     | NO   | PRI | NULL    |       |
| nama_barang | varchar(35) | NO   |     | NULL    |       |
| ukuran      | varchar(10) | NO   |     | NULL    |       |
| warna       | varchar(15) | NO   |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
4 rows in set (0.007 sec)
```

MariaDB [19225003_bab3a]> show tables;
```
+--------------------------+
| Tables_in_19225003_bab3a |
+--------------------------+
| barang                   |
| pedagang                 |
+--------------------------+
2 rows in set (0.001 sec)
```

MariaDB [19225003_bab3a]> alter table barang drop primary key;
Query OK, 0 rows affected (0.030 sec)              
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [19225003_bab3a]> alter table barang add column harga int(10);
Query OK, 0 rows affected (0.012 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [19225003_bab3a]> rename table pedagang to pedagang03;
Query OK, 0 rows affected (0.007 sec)

MariaDB [19225003_bab3a]> alter table barang add primary key (id_barang);
Query OK, 0 rows affected (0.018 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [19225003_bab3a]> alter table pedagang03 drop column no_telp;
Query OK, 0 rows affected (0.012 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [19225003_bab3a]> describe barang;
```
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| id_barang   | char(5)     | NO   | PRI | NULL    |       |
| nama_barang | varchar(35) | NO   |     | NULL    |       |
| ukuran      | varchar(10) | NO   |     | NULL    |       |
| warna       | varchar(15) | NO   |     | NULL    |       |
| harga       | int(10)     | YES  |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
5 rows in set (0.007 sec)
```

MariaDB [19225003_bab3a]> drop database 19225003_bab3b;
Query OK, 0 rows affected, 2 warnings (0.006 sec)

MariaDB [19225003_bab3a]> alter table pedagang03 add column no_hp varchar(20);
Query OK, 0 rows affected (0.010 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [19225003_bab3a]> alter table barang change warna wrn varchar(20);
Query OK, 0 rows affected (0.015 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [19225003_bab3a]> describe barang;
```
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| id_barang   | char(5)     | NO   | PRI | NULL    |       |
| nama_barang | varchar(35) | NO   |     | NULL    |       |
| ukuran      | varchar(10) | NO   |     | NULL    |       |
| wrn         | varchar(20) | YES  |     | NULL    |       |
| harga       | int(10)     | YES  |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
5 rows in set (0.007 sec)
```
MariaDB [19225003_bab3a]> 