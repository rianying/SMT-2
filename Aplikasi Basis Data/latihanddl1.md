rian@Rian Applications % /Applications/XAMPP/xamppfiles/bin/mysql -u root     
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 13
Server version: 10.4.21-MariaDB Source distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> create database komik_coba1;
Query OK, 1 row affected (0.008 sec)

MariaDB [(none)]> create database komik_cobalagi1;
Query OK, 1 row affected (0.003 sec)

MariaDB [(none)]> show databases;
```
+--------------------+
| Database           |
+--------------------+
| db_19225003        |
| db_latihan1        |
| information_schema |
| komik_coba1        |
| komik_cobalagi1    |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
9 rows in set (0.012 sec)
```

MariaDB [(none)]> drop database komik_cobalagi1;
Query OK, 0 rows affected, 2 warnings (0.022 sec)

MariaDB [(none)]> use komik_coba1
Database changed
MariaDB [komik_coba1]> show tables;
Empty set (0.001 sec)

MariaDB [komik_coba1]> create table anggota(id_anggota char(4), nama varchar(20), alamat varchar(30), no_telp varchar(15), tgl_lahir date)
    -> ;
Query OK, 0 rows affected (0.064 sec)

MariaDB [komik_coba1]> show tables;
```
+-----------------------+
| Tables_in_komik_coba1 |
+-----------------------+
| anggota               |
+-----------------------+
1 row in set (0.013 sec)
```

MariaDB [komik_coba1]> create table komik(id_komik char(5), judul varchar(25) NOT NULL, pengarang varchar(30) NOT NULL, thn_terbit year NOT NULL, jenis_komik varchar(15) NOT NULL, PRIMARY KEY (id_komik));
Query OK, 0 rows affected (0.024 sec)

MariaDB [komik_coba1]> show tables;
```
+-----------------------+
| Tables_in_komik_coba1 |
+-----------------------+
| anggota               |
| komik                 |
+-----------------------+
2 rows in set (0.002 sec)
```


MariaDB [komik_coba1]> describe komik;
```
+-------------+-------------+------+-----+---------+-------+
| Field       | Type        | Null | Key | Default | Extra |
+-------------+-------------+------+-----+---------+-------+
| id_komik    | char(5)     | NO   | PRI | NULL    |       |
| judul       | varchar(25) | NO   |     | NULL    |       |
| pengarang   | varchar(30) | NO   |     | NULL    |       |
| thn_terbit  | year(4)     | NO   |     | NULL    |       |
| jenis_komik | varchar(15) | NO   |     | NULL    |       |
+-------------+-------------+------+-----+---------+-------+
5 rows in set (0.026 sec)
```

MariaDB [komik_coba1]> create table pinjam(no_pinjam int(4), id_anggota char(4), id_komik int(5), jumlah int(2));
Query OK, 0 rows affected (0.016 sec)

MariaDB [komik_coba1]> show tables;
```
+-----------------------+
| Tables_in_komik_coba1 |
+-----------------------+
| anggota               |
| komik                 |
| pinjam                |
+-----------------------+
3 rows in set (0.002 sec)
```

MariaDB [komik_coba1]> describe pinjam;
```
+------------+---------+------+-----+---------+-------+
| Field      | Type    | Null | Key | Default | Extra |
+------------+---------+------+-----+---------+-------+
| no_pinjam  | int(4)  | YES  |     | NULL    |       |
| id_anggota | char(4) | YES  |     | NULL    |       |
| id_komik   | int(5)  | YES  |     | NULL    |       |
| jumlah     | int(2)  | YES  |     | NULL    |       |
+------------+---------+------+-----+---------+-------+
4 rows in set (0.009 sec)
```

MariaDB [komik_coba1]> describe anggota
    -> ;
```
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| id_anggota | char(4)     | YES  |     | NULL    |       |
| nama       | varchar(20) | YES  |     | NULL    |       |
| alamat     | varchar(30) | YES  |     | NULL    |       |
| no_telp    | varchar(15) | YES  |     | NULL    |       |
| tgl_lahir  | date        | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
5 rows in set (0.011 sec)
```

MariaDB [komik_coba1]> alter table anggota add column tgl_daftar date;
Query OK, 0 rows affected (0.020 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [komik_coba1]> describe anggota
    -> ;
```
+------------+-------------+------+-----+---------+-------+
| Field      | Type        | Null | Key | Default | Extra |
+------------+-------------+------+-----+---------+-------+
| id_anggota | char(4)     | YES  |     | NULL    |       |
| nama       | varchar(20) | YES  |     | NULL    |       |
| alamat     | varchar(30) | YES  |     | NULL    |       |
| no_telp    | varchar(15) | YES  |     | NULL    |       |
| tgl_lahir  | date        | YES  |     | NULL    |       |
| tgl_daftar | date        | YES  |     | NULL    |       |
+------------+-------------+------+-----+---------+-------+
6 rows in set (0.005 sec)
```

MariaDB [komik_coba1]> rename table anggota to anggota_warnet;
Query OK, 0 rows affected (0.025 sec)

MariaDB [komik_coba1]> show tables;
```
+-----------------------+
| Tables_in_komik_coba1 |
+-----------------------+
| anggota_warnet        |
| komik                 |
| pinjam                |
+-----------------------+
3 rows in set (0.002 sec)
```

MariaDB [komik_coba1]> alter table komik add column status varchar(10);
Query OK, 0 rows affected (0.012 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [komik_coba1]> describe pinjam;
```
+------------+---------+------+-----+---------+-------+
| Field      | Type    | Null | Key | Default | Extra |
+------------+---------+------+-----+---------+-------+
| no_pinjam  | int(4)  | YES  |     | NULL    |       |
| id_anggota | char(4) | YES  |     | NULL    |       |
| id_komik   | int(5)  | YES  |     | NULL    |       |
| jumlah     | int(2)  | YES  |     | NULL    |       |
+------------+---------+------+-----+---------+-------+
4 rows in set (0.007 sec)
```

MariaDB [komik_coba1]> alter table pinjam add primary key (no_pinjam);
Query OK, 0 rows affected (0.026 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [komik_coba1]> rename table pinjam to transaksi;
Query OK, 0 rows affected (0.009 sec)

MariaDB [komik_coba1]> alter table anggota_warnet add primary key (id_anggota);
Query OK, 0 rows affected (0.028 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [komik_coba1]> alter table komik drop column jenis_komik;
Query OK, 0 rows affected (0.018 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [komik_coba1]> alter table transaksi change jumlah jml_komik int(4);
Query OK, 0 rows affected (0.015 sec)
Records: 0  Duplicates: 0  Warnings: 0

MariaDB [komik_coba1]> 