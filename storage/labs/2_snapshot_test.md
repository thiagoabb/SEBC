# Lab 5 Snapshots Test
```
<create directory>
hadoop fs -mkdir /precious
hadoop fs -put SEBC-master.zip /precious
```
```
<allow snapshot dir>
hdfs dfsadmin -allowSnapshot /precious
```
```
<create a snapshot>
hdfs dfs -createSnapshot /precious sebc-hdfs-test
```
```
<list snapshot created>
hadoop fs -ls /precious/.snapshot/sebc-hdfs-test 

< output > 
Found 1 items
-rw-r--r--   3 root root     474919 2018-07-24 20:42 /precious/.snapshot/sebc-hdfs-test/SEBC-master.zip
```
```
< remove original file >
hadoop fs -rm /precious/SEBC-master.zip
```
```
< restore snapshot >
hadoop -fs cp -p /precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /precious
```