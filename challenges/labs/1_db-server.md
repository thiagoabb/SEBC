# Challange 1 - Mariadb DB PROPERTIES and DB's
```
<DB Server Host>

MariaDB [(none)]> SHOW VARIABLES WHERE Variable_name = 'hostname';
+---------------+------------+
| Variable_name | Value      |
+---------------+------------+
| hostname      | cloudera-1 |
+---------------+------------+
1 row in set (0.00 sec)

```

```
<DB Server Version>

MariaDB [(none)]> status
--------------
mysql  Ver 15.1 Distrib 5.5.56-MariaDB, for Linux (x86_64) using readline 5.1

Connection id:          5
Current database:
Current user:           root@localhost
SSL:                    Not in use
Current pager:          stdout
Using outfile:          ''
Using delimiter:        ;
Server:                 MariaDB
Server version:         5.5.56-MariaDB MariaDB Server
Protocol version:       10
Connection:             Localhost via UNIX socket
Server characterset:    latin1
Db     characterset:    latin1
Client characterset:    utf8
Conn.  characterset:    utf8
UNIX socket:            /var/lib/mysql/mysql.sock
Uptime:                 4 min 22 sec

Threads: 1  Questions: 15  Slow queries: 0  Opens: 0  Flush tables: 2  Open tables: 26  Queries per second avg: 0.057
--------------

```

```
<DB Databases>

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
+--------------------+
8 rows in set (0.01 sec)

```