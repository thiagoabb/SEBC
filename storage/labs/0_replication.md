# Lab 3 Replication HDFS
```
<Create Dirs>

-- Create myid directory
hadoop fs -mkdir /thiagoabb
hadoop fs -mkdir -p /thiagoabb/target
```

```
< TERAGEN >
- Create file ~500MB (origin directory)
hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen 5000000 /thiagoabb/origin
```

```
< Distcp >
hadoop distcp hdfs://18.222.54.165:8020/user/uderttree/origin hdfs://40.70.201.41:8020/thiagoabb/target
```

```
<Brownse results>
hdfs fsck /thiagoabb/target -files -blocks
< outputs >
Connecting to namenode via http://cloudera2.3myyf0oxarxezaohzgk2qozj0c.cx.internal.cloudapp.net:50070
FSCK started by hdfs (auth:SIMPLE) from /10.0.1.4 for path /thiagoabb/target at Tue Jul 24 22:30:33 UTC 2018
/thiagoabb/target <dir>
/thiagoabb/target/500mbfile <dir>
/thiagoabb/target/500mbfile/_SUCCESS 0 bytes, 0 block(s):  OK

/thiagoabb/target/origin <dir>
/thiagoabb/target/origin/_SUCCESS 0 bytes, 0 block(s):  OK

/thiagoabb/target/origin/part-m-00000 500000000 bytes, 4 block(s):  OK
0. BP-448093678-10.0.1.5-1532458041947:blk_1073744501_3677 len=134217728 Live_repl=3
1. BP-448093678-10.0.1.5-1532458041947:blk_1073744502_3678 len=134217728 Live_repl=3
2. BP-448093678-10.0.1.5-1532458041947:blk_1073744503_3679 len=134217728 Live_repl=3
3. BP-448093678-10.0.1.5-1532458041947:blk_1073744504_3680 len=97346816 Live_repl=3

Status: HEALTHY
 Total size:    500000000 B
 Total dirs:    3
 Total files:   3
 Total symlinks:                0 (Files currently being written: 4)
 Total blocks (validated):      4 (avg. block size 125000000 B) (Total open file blocks (not validated): 4)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Jul 24 22:30:33 UTC 2018 in 3 milliseconds
```
```
hdfs fsck /thiago/origin -files -blocks
< outputs >
Connecting to namenode via http://cloudera2.3myyf0oxarxezaohzgk2qozj0c.cx.internal.cloudapp.net:50070
FSCK started by hdfs (auth:SIMPLE) from /10.0.1.4 for path /thiagoabb/target at Tue Jul 24 22:30:33 UTC 2018
/thiagoabb/target <dir>
/thiagoabb/target/500mbfile <dir>
/thiagoabb/target/500mbfile/_SUCCESS 0 bytes, 0 block(s):  OK

/thiagoabb/target/origin <dir>
/thiagoabb/target/origin/_SUCCESS 0 bytes, 0 block(s):  OK

/thiagoabb/target/origin/part-m-00000 500000000 bytes, 4 block(s):  OK
0. BP-448093678-10.0.1.5-1532458041947:blk_1073744501_3677 len=134217728 Live_repl=3
1. BP-448093678-10.0.1.5-1532458041947:blk_1073744502_3678 len=134217728 Live_repl=3
2. BP-448093678-10.0.1.5-1532458041947:blk_1073744503_3679 len=134217728 Live_repl=3
3. BP-448093678-10.0.1.5-1532458041947:blk_1073744504_3680 len=97346816 Live_repl=3

Status: HEALTHY
 Total size:    500000000 B
 Total dirs:    3
 Total files:   3
 Total symlinks:                0 (Files currently being written: 4)
 Total blocks (validated):      4 (avg. block size 125000000 B) (Total open file blocks (not validated): 4)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Jul 24 22:30:33 UTC 2018 in 3 milliseconds


The filesystem under path '/thiagoabb/target' is HEALTHY
[hdfs@cloudera1 cloudera]$ hdfs fsck /thiago/origin -files -blocks
Connecting to namenode via http://cloudera2.3myyf0oxarxezaohzgk2qozj0c.cx.internal.cloudapp.net:50070
FSCK started by hdfs (auth:SIMPLE) from /10.0.1.4 for path /thiago/origin at Tue Jul 24 22:30:58 UTC 2018

```

