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
