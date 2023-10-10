rian@Rian Applications % /Applications/XAMPP/xamppfiles/bin/mysql -u root
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 14
Server version: 10.4.21-MariaDB Source distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> create database db_les_private;
Query OK, 1 row affected (0.004 sec)

MariaDB [(none)]> use db_les_private
Database changed
MariaDB [db_les_private]> create table siswa(nis char (6) NOT NULL PRIMARY KEY, nama varchar(40) not null, tgl date not null, kelas varchar(15) not null, no_telp varchar(18) not null);
Query OK, 0 rows affected (0.039 sec)

MariaDB [db_les_private]> show tables;
+--------------------------+
| Tables_in_db_les_private |
+--------------------------+
| siswa                    |
+--------------------------+
1 row in set (0.002 sec)

MariaDB [db_les_private]> describe siswa;
```
+---------+-------------+------+-----+---------+-------+
| Field   | Type        | Null | Key | Default | Extra |
+---------+-------------+------+-----+---------+-------+
| nis     | char(6)     | NO   | PRI | NULL    |       |
| nama    | varchar(40) | NO   |     | NULL    |       |
| tgl     | date        | NO   |     | NULL    |       |
| kelas   | varchar(15) | NO   |     | NULL    |       |
| no_telp | varchar(18) | NO   |     | NULL    |       |
+---------+-------------+------+-----+---------+-------+
5 rows in set (0.017 sec)
```

MariaDB [db_les_private]> alter table siswa change nama nama_siswa  varchar(30) not null;
Query OK, 0 rows affected (0.035 sec)              
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [db_les_private]> alter table siswa change tgl tgl_lahir date not null;
Query OK, 0 rows affected (0.011 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [db_les_private]> alter table siswa change kelas kelas_siswa varchar(20) not null;
Query OK, 0 rows affected (0.008 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [db_les_private]> alter table siswa drop column no_telp;
Query OK, 0 rows affected (0.011 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [db_les_private]> rename table siswa to siswa_baru;
Query OK, 0 rows affected (0.006 sec)

MariaDB [db_les_private]> describe siswa_baru;
```
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| nis         | char(6)     | NO   | PRI | NULL    |       |
| nama_siswa  | varchar(30) | NO   |     | NULL    |       |
| tgl_lahir   | date        | NO   |     | NULL    |       |
| kelas_siswa | varchar(20) | NO   |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
4 rows in set (0.007 sec)
```

MariaDB [db_les_private]> create table tutor(id_tutor char(8) not null primary key, nama_tutor varchar(30) not null, jenis varchar(20) not null, jml_kelas smallint(4) not null);
Query OK, 0 rows affected (0.013 sec)

MariaDB [db_les_private]> create table ruang(id_ruang char(3), nama_ruang varchar(10));
Query OK, 0 rows affected (0.010 sec)

MariaDB [db_les_private]> describe tutor;
```
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| id_tutor   | char(8)     | NO   | PRI | NULL    |       |
| nama_tutor | varchar(30) | NO   |     | NULL    |       |
| jenis      | varchar(20) | NO   |     | NULL    |       |
| jml_kelas  | smallint(4) | NO   |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
4 rows in set (0.005 sec)
```

MariaDB [db_les_private]> describe ruang;
```
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| id_ruang   | char(3)     | YES  |     | NULL    |       |
| nama_ruang | varchar(10) | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
2 rows in set (0.006 sec)
```

MariaDB [db_les_private]> alter table tutor modify jml_kelas int(4);
Query OK, 0 rows affected (0.028 sec)              
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [db_les_private]> describe ruang;
```
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| id_ruang   | char(3)     | YES  |     | NULL    |       |
| nama_ruang | varchar(10) | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
2 rows in set (0.007 sec)
```

MariaDB [db_les_private]> alter table ruang modify id_ruang int;
Query OK, 0 rows affected (0.024 sec)              
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [db_les_private]> drop database ruang;
ERROR 1008 (HY000): Can't drop database 'ruang'; database doesn't exist
MariaDB [db_les_private]> drop table ruang;
Query OK, 0 rows affected (0.007 sec)

MariaDB [db_les_private]> rename table tutor to tutor_les;
Query OK, 0 rows affected (0.005 sec)

MariaDB [db_les_private]> show tables;
```
+--------------------------+
| Tables_in_db_les_private |
+--------------------------+
| siswa_baru               |
| tutor_les                |
+--------------------------+
2 rows in set (0.001 sec)
```

MariaDB [db_les_private]> 