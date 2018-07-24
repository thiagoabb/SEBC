# Lab 4 Benchamar tests HDFS
```
< Create Dirs >
hadoop fs -mkdir -p /user/thiagoabb
```
```
< Run Teragen with properties >
time hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapreduce.job.maps=4 -Ddfs.blocksize=32M 107000000 /user/thiagoabb/teragen 

<JOB output>
File System Counters
        FILE: Number of bytes read=276333
        FILE: Number of bytes written=572083
        FILE: Number of read operations=0
        FILE: Number of large read operations=0
        FILE: Number of write operations=0
        HDFS: Number of bytes read=0
        HDFS: Number of bytes written=10700000000
        HDFS: Number of read operations=4
        HDFS: Number of large read operations=0
        HDFS: Number of write operations=3
Map-Reduce Framework
        Map input records=107000000
        Map output records=107000000
        Input split bytes=83
        Spilled Records=0
        Failed Shuffles=0
        Merged Map outputs=0
        GC time elapsed (ms)=1367
        Total committed heap usage (bytes)=240648192
org.apache.hadoop.examples.terasort.TeraGen$Counters
        CHECKSUM=229790349692337776
File Input Format Counters
        Bytes Read=0
File Output Format Counters
        Bytes Written=10700000000
		
< HDFS OUTPUT >
[thiagoabb@cloudera1 cloudera-scm-server]$ hadoop fs -ls /user/thiagoabb/teragen
Found 2 items
-rw-r--r--   3 thiagoabb supergroup           0 2018-07-24 20:04 /user/thiagoabb/teragen/_SUCCESS
-rw-r--r--   3 thiagoabb supergroup 10700000000 2018-07-24 20:04 /user/thiagoabb/teragen/part-m-00000
				
<time result>
real    2m33.221s
user    2m15.526s
sys     0m10.062s
```

```
< Run Terasort >
time hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/thiagoabb/teragen  /user/thiagoabb/terasort 

< JOB output >
18/07/24 20:25:51 INFO mapreduce.Job: Counters: 35
        File System Counters
                FILE: Number of bytes read=33341182860
                FILE: Number of bytes written=1814343340068
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1726514340700
                HDFS: Number of bytes written=10700000000
                HDFS: Number of read operations=110721
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=642
        Map-Reduce Framework
                Map input records=107000000
                Map output records=107000000
                Map output bytes=10914000000
                Map output materialized bytes=11128001914
                Input split bytes=55506
                Combine input records=0
                Combine output records=0
                Reduce input groups=107000000
                Reduce shuffle bytes=11128001914
                Reduce input records=107000000
                Reduce output records=107000000
                Spilled Records=317309009
                Shuffled Maps =319
                Failed Shuffles=0
                Merged Map outputs=319
                GC time elapsed (ms)=99887
                Total committed heap usage (bytes)=85490925568
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=10700000000
        File Output Format Counters
                Bytes Written=10700000000
18/07/24 20:25:51 INFO terasort.TeraSort: done

< HDFS OUTPUT >
[thiagoabb@cloudera1 cloudera-scm-server]$ hadoop fs -ls /user/thiagoabb/terasort
Found 3 items
-rw-r--r--   3 thiagoabb supergroup           0 2018-07-24 20:25 /user/thiagoabb/terasort/_SUCCESS
-rw-r--r--  10 thiagoabb supergroup           0 2018-07-24 20:06 /user/thiagoabb/terasort/_partition.lst
-rw-r--r--   3 thiagoabb supergroup 10700000000 2018-07-24 20:25 /user/thiagoabb/terasort/part-r-00000

< TIME >
real    19m18.117s
user    17m43.393s
sys     1m26.374s

```