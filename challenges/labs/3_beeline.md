#Challenge 3: Beeline
```
beeline
!connect jdbc:hive2://10.0.1.5:10000/default


<beeline output>
No rows affected (0.036 seconds)
1: jdbc:hive2://10.0.1.5:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20180727175151_8a4fe4de-df63-4c3a-8ca8-719cda957caf): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20180727175151_8a4fe4de-df63-4c3a-8ca8-719cda957caf); Time taken: 0.005 seconds
INFO  : Executing command(queryId=hive_20180727175151_8a4fe4de-df63-4c3a-8ca8-719cda957caf): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20180727175151_8a4fe4de-df63-4c3a-8ca8-719cda957caf); Time taken: 0.03 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.054 seconds)
```