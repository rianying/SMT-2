```markdown```
```shell
rian@Rian ~ % /Applications/XAMPP/xamppfiles/bin/mysql -u root
```

Welcome to the MariaDB monitor.  Commands end with `;` or `\g`.
Your MariaDB connection id is 14
Server version: 10.4.21-MariaDB Source distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

```sql
MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| db_latihan1        |
| information_schema |
| mysql              |
| performance_schema |
| phpmyadmin         |
| test               |
+--------------------+
6 rows in set (0.011 sec)

MariaDB [(none)]> use mysql;
```

Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with `-A`

```sql
Database changed
MariaDB [mysql]> select user, host from mysql.user;
+-------+-----------+
| user  | host      |
+-------+-----------+
| root  | 127.0.0.1 |
| root  | ::1       |
|       | localhost |
| pma   | localhost |
| rian  | localhost |
| rian2 | localhost |
| root  | localhost |
+-------+-----------+
7 rows in set (0.007 sec)

MariaDB [mysql]> create user '19225003_coba2'@'localhost' identified by '12345';
Query OK, 0 rows affected (0.012 sec)

MariaDB [mysql]> create user '19225003_cobalagi'@'localhost';
Query OK, 0 rows affected (0.003 sec)

MariaDB [mysql]> select user, host from mysql.user;
+-------------------+-----------+
| user              | host      |
+-------------------+-----------+
| root              | 127.0.0.1 |
| root              | ::1       |
|                   | localhost |
| 19225003_coba2    | localhost |
| 19225003_cobalagi | localhost |
| pma               | localhost |
| rian              | localhost |
| rian2             | localhost |
| root              | localhost |
+-------------------+-----------+
9 rows in set (0.002 sec)

MariaDB [mysql]> create database db_19225003;
Query OK, 1 row affected (0.001 sec)

MariaDB [mysql]> use db_19225003;
```

Database changed

```sql
MariaDB [db_19225003]> create table buku(Kd_buku char(5), Judul varchar(40), Penulis varchar(35), Penerbit varchar(35));
Query OK, 0 rows affected (0.031 sec)

MariaDB [db_19225003]> create table katalog(Kode char(6), Nama varchar(30));
Query OK, 0 rows affected (0.010 sec)

MariaDB [db_19225003]> show tables;
```

```sql
+-----------------------+
| Tables_in_db_19225003 |
+-----------------------+
| buku                  |
| katalog               |
+-----------------------+
2 rows in set (0.001 sec)

MariaDB [db_19225003]> desc buku;
```

```sql
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| Kd_buku  | char(5)     | YES  |     | NULL    |       |
| Judul    | varchar(40) | YES  |     | NULL    |       |
| Penulis  | varchar(35) | YES  |     | NULL    |       |
| Penerbit | varchar(35) | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
4 rows in set (0.013 sec)

MariaDB [db_19225003]> desc katalog;
```

```sql
+-------+-------------+------+-----+---------+-------+
| Field | Type        | Null | Key | Default | Extra |
+-------+-------------+------+-----+---------+-------+
| Kode  | char(6)     | YES  |     | NULL    |       |
| Nama  | varchar(30) | YES  |     | NULL    |       |
+-------+-------------+------+-----+---------+-------+
2 rows in set (0.005 sec)

MariaDB [db_19225003]> grant all on db_19225003 to '19225003_coba2';
```

```sql
ERROR 1133 (28000): Can't find any matching row in the user table

MariaDB [db_19225003]> grant all on db_19225003.buku to '19225003_coba2';
```

```sql
ERROR 1133 (28000): Can't find any matching row in the user table

MariaDB [db_19225003]> grant all on db_19225003 to '19225003_coba2'@'localhost';
Query OK, 0 rows affected (0.005 sec)

MariaDB [db_19225003]> drop user 19225003_cobalagi@localhost;
Query OK, 0 rows affected (0.006 sec)

MariaDB [db_19225003]> exit
```

Bye

```shell
rian@Rian ~ % /Applications/XAMPP/xamppfiles/bin/mysql -u 19225003_coba2
```

```sql
ERROR 1045 (28000): Access denied for user '19225003_coba2'@'localhost' (using password: NO)

rian@Rian ~ % /Applications/XAMPP/xamppfiles/bin/mysql -u 19225003_coba2 12345
```

```sql
ERROR 1045 (28000): Access denied for user '19225003_coba2'@'localhost' (using password: NO)

rian@Rian ~ % /Applications/XAMPP/xamppfiles/bin/mysql -u 19225003_coba2 -p 12345
```

```sql
Enter password: 

ERROR 1044 (42000): Access denied for user '19225003_coba2'@'localhost' to database '12345'

rian@Rian ~ % /Applications/XAMPP/xamppfiles/bin/mysql -u 19225003_coba2 -p
```

```sql
Enter password: 

Welcome to the MariaDB monitor.  Commands end with `;` or `\g`.
Your MariaDB connection id is 18
Server version: 10.4.21-MariaDB Source distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

```sql
MariaDB [(none)]> show databases;
+--------------------+
| Database

           |
+--------------------+
| db_19225003        |
| information_schema |
| test               |
+--------------------+
3 rows in set (0.002 sec)

MariaDB [(none)]>
```

Feel free to use this Markdown formatting in your documentation or wherever you need it.