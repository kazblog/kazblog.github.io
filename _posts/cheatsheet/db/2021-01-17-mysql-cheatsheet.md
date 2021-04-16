---
layout: post
title:  "MySQLのチートシート"
date:   2021-01-02 12:39:36 +0900
categories: cheatsheet
tags: mysql
permalink: /mysql-cheatsheet
excerpt_separator: <!--more-->
---

<!--more-->

DB内に入る、テーブル見る、DBみる、テーブルを消すのコマンド

```
# mysql -u root -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 180
Server version: 8.0.22 MySQL Community Server - GPL

Copyright (c) 2000, 2020, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| myapp_development  |
| myapp_test         |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
6 rows in set (0.13 sec)

mysql> use myapp_development
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

Database changed
mysql> show tables;
+--------------------------------+
| Tables_in_myapp_development    |
+--------------------------------+
| action_text_rich_texts         |
| active_storage_attachments     |
| active_storage_blobs           |
| active_storage_variant_records |
| ar_internal_metadata           |
| comments                       |
| likes                          |
| posts                          |
| relationships                  |
| schema_migrations              |
| users                          |
+--------------------------------+
11 rows in set (0.01 sec)

mysql> drop table likes;
Query OK, 0 rows affected (0.10 sec)

mysql> select * from users;
+----+--------------+--------------------------+----------------------------+----------------------------+--------------------------------------------------------------+-------+--------------------------------------------------------------+-----------+---------------------+------+--------------------+--------------+
| id | name         | email                    | created_at                 | updated_at                 | password_digest                                              | admin | activation_digest                                            | activated | activated_at        | year | bio                | avatar       |
+----+--------------+--------------------------+----------------------------+----------------------------+--------------------------------------------------------------+-------+--------------------------------------------------------------+-----------+---------------------+------+--------------------+--------------+
|  1 | main-user    | main@gmail.com           | 2021-01-25 10:17:25.721222 | 2021-01-25 10:17:25.721222 | $2a$10$Patg7txAgletol4ENYetAu3SZlYxfmRQf6TKC5OSHjjhXZVJlLU1a |     1 | $2a$10$Z.jQna2unJgmXA5C3jzOeeEI4Bg4JnFwW0HUyUvq1Q6regnCcC72i |         1 | 2021-01-25 10:17:24 | 1?   | hello!             | the-main.jpg |
|  2 | ???????????? | smooth_login@example.com | 2021-01-25 10:17:28.367389 | 2021-01-25 10:17:28.367389 | $2a$10$lRhSUjygB9qeIZyFs6cN2eV8zmEl.RE8jrrrQILo8zIjslIAe9aoS |     0 | $2a$10$ARbNOVr5Y0V1Yi5/9PMpnew0B7tY4Zb8/cx6sfH/.USx/jpQGfW0y |         1 | 2021-01-25 10:17:27 | 3?   | hello!???????????? | the-main.jpg |
+----+--------------+--------------------------+----------------------------+----------------------------+--------------------------------------------------------------+-------+--------------------------------------------------------------+-----------+---------------------+------+--------------------+--------------+
2 rows in set (0.01 sec)



テーブル一つ ＝ 一つのデータベース
mysql> create database user;
Query OK, 1 row affected (0.03 sec)

使うデータベースを設定
mysql> use user
Database changed


テーブルを作成し、その中に列も追加する。
mysql> create table user (
    -> id int);
Query OK, 0 rows affected (0.13 sec)

mysql> show tables;
+----------------+
| Tables_in_user |
+----------------+
| user           |
+----------------+
1 row in set (0.01 sec)

選択したデータベースの中身を見る
mysql> desc user;
+-------+------+------+-----+---------+-------+
| Field | Type | Null | Key | Default | Extra |
+-------+------+------+-----+---------+-------+
| id    | int  | YES  |     | NULL    |       |
+-------+------+------+-----+---------+-------+
1 row in set (0.03 sec)

テーブルの列を追加する。

mysql> desc user;
+-------+------+------+-----+---------+-------+
| Field | Type | Null | Key | Default | Extra |
+-------+------+------+-----+---------+-------+
| id    | int  | YES  |     | NULL    |       |
+-------+------+------+-----+---------+-------+
1 row in set (0.01 sec)

mysql> alter table user
    -> add name text;
Query OK, 0 rows affected (0.14 sec)
Records: 0  Duplicates: 0  Warnings: 0

mysql> desc user;
+-------+------+------+-----+---------+-------+
| Field | Type | Null | Key | Default | Extra |
+-------+------+------+-----+---------+-------+
| id    | int  | YES  |     | NULL    |       |
| name  | text | YES  |     | NULL    |       |
+-------+------+------+-----+---------+-------+
2 rows in set (0.01 sec



```


## DBをdropしたい時のコマンど(rails5以降有効)

```
RAILS_ENV=development DISABLE_DATABASE_ENVIRONMENT_CHECK=1 bundle exec rake db:drop
```
developmentの箇所は、他にも  
default,
development,
test,
productionなどのチョイスがある。

↓<br>

```
rails db:create RAILS_ENV=development
```

```
rails db:migrate RAILS_ENV=development
```
