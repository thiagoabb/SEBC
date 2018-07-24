# Lab 3 Replication HDFS
```
<Create Dirs>

-- Create myid directory
hadoop fs -mkdir /thiagoabb

-- Create partnner directory
hadoop fs -mkdir -p /andreiamaia/target
```

```
< TERAGEN >
- Create file ~500MB (origin directory)
hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen 5000000 /thiagoabb/origin
```

```
< Distcp >
hadoop distcp hdfs://nn1:8020/andreiamaia/origin hdfs://40.70.201.41:8020/andreiamaia/target
```

```
<Brownse results>
hdfs fsck /andreiamaia/target -files -blocks
< outputs >


hdfs fsck /thiago/origin -files -blocks
< outputs >

```

