#Challenge 4: HDFS tests
```
<Teragen>
[goldengate@cloudera-2 ~]$ time hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapred.map.tasks=8 -Ddfs.blocksize=64M -Dmapreduce.map.memory.mb=768 65536000 /user/goldengate/tgen

<output>
18/07/27 17:58:03 INFO client.RMProxy: Connecting to ResourceManager at cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net/10.0.1.5:8032
18/07/27 17:58:04 INFO terasort.TeraSort: Generating 65536000 using 8
18/07/27 17:58:04 INFO mapreduce.JobSubmitter: number of splits:8
18/07/27 17:58:04 INFO Configuration.deprecation: mapred.map.tasks is deprecated. Instead, use mapreduce.job.maps
18/07/27 17:58:04 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1532713567438_0001
18/07/27 17:58:05 INFO impl.YarnClientImpl: Submitted application application_1532713567438_0001
18/07/27 17:58:05 INFO mapreduce.Job: The url to track the job: http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:8088/proxy/application_1532713567438_0001/
18/07/27 17:58:05 INFO mapreduce.Job: Running job: job_1532713567438_0001
18/07/27 17:58:11 INFO mapreduce.Job: Job job_1532713567438_0001 running in uber mode : false
18/07/27 17:58:11 INFO mapreduce.Job:  map 0% reduce 0%
18/07/27 17:58:23 INFO mapreduce.Job:  map 6% reduce 0%
18/07/27 17:58:24 INFO mapreduce.Job:  map 20% reduce 0%
18/07/27 17:58:25 INFO mapreduce.Job:  map 26% reduce 0%
18/07/27 17:58:26 INFO mapreduce.Job:  map 31% reduce 0%
18/07/27 17:58:27 INFO mapreduce.Job:  map 39% reduce 0%
18/07/27 17:58:28 INFO mapreduce.Job:  map 44% reduce 0%
18/07/27 17:58:29 INFO mapreduce.Job:  map 48% reduce 0%
18/07/27 17:58:30 INFO mapreduce.Job:  map 57% reduce 0%
18/07/27 17:58:31 INFO mapreduce.Job:  map 62% reduce 0%
18/07/27 17:58:32 INFO mapreduce.Job:  map 66% reduce 0%
18/07/27 17:58:33 INFO mapreduce.Job:  map 73% reduce 0%
18/07/27 17:58:34 INFO mapreduce.Job:  map 77% reduce 0%
18/07/27 17:58:35 INFO mapreduce.Job:  map 81% reduce 0%
18/07/27 17:58:36 INFO mapreduce.Job:  map 88% reduce 0%
18/07/27 17:58:37 INFO mapreduce.Job:  map 98% reduce 0%
18/07/27 17:58:38 INFO mapreduce.Job:  map 100% reduce 0%
18/07/27 17:58:38 INFO mapreduce.Job: Job job_1532713567438_0001 completed successfully
18/07/27 17:58:38 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=991368
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=682
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=32
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=8
                Other local map tasks=8
                Total time spent by all maps in occupied slots (ms)=191183
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=191183
                Total vcore-seconds taken by all map tasks=191183
                Total megabyte-seconds taken by all map tasks=195771392
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Input split bytes=682
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=2270
                CPU time spent (ms)=118300
                Physical memory (bytes) snapshot=2231152640
                Virtual memory (bytes) snapshot=10823053312
                Total committed heap usage (bytes)=4084727808
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=140750829423462787
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=6553600000
				
<Time result >
real    0m37.034s
user    0m4.625s
sys     0m0.270s
```

```
<LS >
[goldengate@cloudera-2 ~]$ hdfs dfs -ls /user/goldengate/tgen
Found 9 items
-rw-r--r--   3 goldengate bridge          0 2018-07-27 17:58 /user/goldengate/tgen/_SUCCESS
-rw-r--r--   3 goldengate bridge  819200000 2018-07-27 17:58 /user/goldengate/tgen/part-m-00000
-rw-r--r--   3 goldengate bridge  819200000 2018-07-27 17:58 /user/goldengate/tgen/part-m-00001
-rw-r--r--   3 goldengate bridge  819200000 2018-07-27 17:58 /user/goldengate/tgen/part-m-00002
-rw-r--r--   3 goldengate bridge  819200000 2018-07-27 17:58 /user/goldengate/tgen/part-m-00003
-rw-r--r--   3 goldengate bridge  819200000 2018-07-27 17:58 /user/goldengate/tgen/part-m-00004
-rw-r--r--   3 goldengate bridge  819200000 2018-07-27 17:58 /user/goldengate/tgen/part-m-00005
-rw-r--r--   3 goldengate bridge  819200000 2018-07-27 17:58 /user/goldengate/tgen/part-m-00006
-rw-r--r--   3 goldengate bridge  819200000 2018-07-27 17:58 /user/goldengate/tgen/part-m-00007
```

```
<FSCK>
[goldengate@cloudera-2 ~]$ hadoop fsck -blocks /user/goldengate
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:50070
FSCK started by goldengate (auth:SIMPLE) from /10.0.1.5 for path /user/goldengate at Fri Jul 27 18:01:45 UTC 2018
.........Status: HEALTHY
 Total size:    6553600000 B
 Total dirs:    3
 Total files:   9
 Total symlinks:                0
 Total blocks (validated):      104 (avg. block size 63015384 B)
 Minimally replicated blocks:   104 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Fri Jul 27 18:01:45 UTC 2018 in 6 milliseconds


The filesystem under path '/user/goldengate' is HEALTHY


```