# Lab 1 sentry-test
```
< test without admin role >

0: jdbc:hive2://10.0.0.5:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20180726000101_dec51cf1-ba94-4faf-b27f-b544b298a979): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20180726000101_dec51cf1-ba94-4faf-b27f-b544b298a979); Time taken: 0.054 seconds
INFO  : Executing command(queryId=hive_20180726000101_dec51cf1-ba94-4faf-b27f-b544b298a979): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20180726000101_dec51cf1-ba94-4faf-b27f-b544b298a979); Time taken: 0.117 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+

```
```
< test with admin role created >
CREATE ROLE sentry_admin;
GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
GRANT ROLE sentry_admin TO GROUP thiagoabb;

0: jdbc:hive2://10.0.0.5:10000/default> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20180726000303_9b3b0f9f-ced8-4545-9829-c7c0a9e733d8): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20180726000303_9b3b0f9f-ced8-4545-9829-c7c0a9e733d8); Time taken: 0.081 seconds
INFO  : Executing command(queryId=hive_20180726000303_9b3b0f9f-ced8-4545-9829-c7c0a9e733d8): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20180726000303_9b3b0f9f-ced8-4545-9829-c7c0a9e733d8); Time taken: 0.122 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
```

```
< George/Ferdinand Roles>
CREATE ROLE reads;
CREATE ROLE writes;
Grant read privilege for all tables to reads
GRANT SELECT ON DATABASE default TO ROLE reads;
GRANT ROLE reads TO GROUP selector;
Grant INSERT privilege for default.sample07 to 'writes':
REVOKE ALL ON DATABASE default FROM ROLE writes;
GRANT INSERT ON default.sample_07 TO ROLE writes;
GRANT ROLE writes TO GROUP inserters; 
```

```
<George validation>
[root@cloudera-1 ~]# kinit george
Password for george@CLOUDERA:
[root@cloudera-1 ~]# beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://10.0.0.5:10000/default;principal=hive/cloudera-2.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net@CLOUDERA
scan complete in 1ms
Connecting to jdbc:hive2://10.0.0.5:10000/default;principal=hive/cloudera-2.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net@CLOUDERA
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://10.0.0.5:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20180726000707_8ba204e9-67c8-4dd2-a8bd-adee3f3ac0e2): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20180726000707_8ba204e9-67c8-4dd2-a8bd-adee3f3ac0e2); Time taken: 0.062 seconds
INFO  : Executing command(queryId=hive_20180726000707_8ba204e9-67c8-4dd2-a8bd-adee3f3ac0e2): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20180726000707_8ba204e9-67c8-4dd2-a8bd-adee3f3ac0e2); Time taken: 0.16 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.343 seconds)

```

```
<Ferdinand validation>
[root@cloudera-1 ~]# kinit ferdinand
Password for ferdinand@CLOUDERA:
[root@cloudera-1 ~]# beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://10.0.0.5:10000/default;principal=hive/cloudera-2.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net@CLOUDERA
scan complete in 2ms
Connecting to jdbc:hive2://10.0.0.5:10000/default;principal=hive/cloudera-2.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net@CLOUDERA
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://10.0.0.5:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20180726000909_58ee9831-fb4c-4367-8653-3c6c78ee4879): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20180726000909_58ee9831-fb4c-4367-8653-3c6c78ee4879); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20180726000909_58ee9831-fb4c-4367-8653-3c6c78ee4879): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20180726000909_58ee9831-fb4c-4367-8653-3c6c78ee4879); Time taken: 0.137 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.317 seconds)

```