rian@Rian Applications % /Applications/XAMPP/xamppfiles/bin/mysql -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 18
Server version: 10.4.21-MariaDB Source distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> create database DB_19225003;
Query OK, 1 row affected (0.002 sec)

MariaDB [(none)]> show database;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MariaDB server version for the right syntax to use near 'database' at line 1
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| 19225003_bab3a     |
| DB_19225003        |
| DB_Jualan_19225003 |
| db_latihan1        |
| db_les_private     |
| information_schema |
| komik_coba1        |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
11 rows in set (0.008 sec)

MariaDB [(none)]> use DB_19225003;
Database changed
MariaDB [DB_19225003]> create table buku (kd_buku char(5), judul varchar(40), penulis varchar(35), penerbit varchar(35));
Query OK, 0 rows affected (0.020 sec)

MariaDB [DB_19225003]> create table katalog (kode char(6), nama varchar(30));
Query OK, 0 rows affected (0.016 sec)

MariaDB [DB_19225003]> show tables;
```
+-----------------------+
| Tables_in_DB_19225003 |
+-----------------------+
| buku                  |
| katalog               |
+-----------------------+
2 rows in set (0.002 sec)
```

MariaDB [DB_19225003]> describe buku;
```
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| kd_buku  | char(5)     | YES  |     | NULL    |       |
| judul    | varchar(40) | YES  |     | NULL    |       |
| penulis  | varchar(35) | YES  |     | NULL    |       |
| penerbit | varchar(35) | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
4 rows in set (0.014 sec)
```

MariaDB [DB_19225003]> describe katalog;
```
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| kode  | char(6)     | YES  |     | NULL    |       |
| nama  | varchar(30) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
2 rows in set (0.006 sec)
```

MariaDB [DB_19225003]> 