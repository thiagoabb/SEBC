#Challenge 5: Kerberized Terasort
```
< command>
time hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/goldengate/tgen /user/goldengate/tsort

<output >
[root@cloudera-2 ~]# time hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/goldengate/tgen /user/goldengate/tsort
18/07/27 18:20:56 INFO terasort.TeraSort: starting
18/07/27 18:20:58 INFO hdfs.DFSClient: Created token for goldengate: HDFS_DELEGATION_TOKEN owner=goldengate@THIAGOABB.SFO, renewer=yarn, realUser=, issueDate=1532715657984, maxDate=1533320457984, sequenceNumber=1, masterKeyId=2 on 10.0.1.5:8020
18/07/27 18:20:58 INFO security.TokenCache: Got dt for hdfs://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.1.5:8020, Ident: (token for goldengate: HDFS_DELEGATION_TOKEN owner=goldengate@THIAGOABB.SFO, renewer=yarn, realUser=, issueDate=1532715657984, maxDate=1533320457984, sequenceNumber=1, masterKeyId=2)
18/07/27 18:20:58 INFO input.FileInputFormat: Total input paths to process : 8
Spent 348ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 353ms
Sampling 10 splits of 104
Making 6 from 100000 sampled records
Computing parititions took 996ms
Spent 1351ms computing partitions.
18/07/27 18:20:59 INFO client.RMProxy: Connecting to ResourceManager at cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net/10.0.1.5:8032
18/07/27 18:20:59 INFO mapreduce.JobSubmitter: number of splits:104
18/07/27 18:20:59 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1532715543477_0001
18/07/27 18:20:59 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.1.5:8020, Ident: (token for goldengate: HDFS_DELEGATION_TOKEN owner=goldengate@THIAGOABB.SFO, renewer=yarn, realUser=, issueDate=1532715657984, maxDate=1533320457984, sequenceNumber=1, masterKeyId=2)
18/07/27 18:21:00 INFO impl.YarnClientImpl: Submitted application application_1532715543477_0001
18/07/27 18:21:00 INFO mapreduce.Job: The url to track the job: http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:8088/proxy/application_1532715543477_0001/
18/07/27 18:21:00 INFO mapreduce.Job: Running job: job_1532715543477_0001
18/07/27 18:21:10 INFO mapreduce.Job: Job job_1532715543477_0001 running in uber mode : false
18/07/27 18:21:10 INFO mapreduce.Job:  map 0% reduce 0%
18/07/27 18:21:18 INFO mapreduce.Job:  map 2% reduce 0%
18/07/27 18:21:19 INFO mapreduce.Job:  map 3% reduce 0%
18/07/27 18:21:24 INFO mapreduce.Job:  map 7% reduce 0%
18/07/27 18:21:25 INFO mapreduce.Job:  map 11% reduce 0%
18/07/27 18:21:26 INFO mapreduce.Job:  map 13% reduce 0%
18/07/27 18:21:34 INFO mapreduce.Job:  map 20% reduce 0%
18/07/27 18:21:35 INFO mapreduce.Job:  map 23% reduce 0%
18/07/27 18:21:36 INFO mapreduce.Job:  map 24% reduce 0%
18/07/27 18:21:42 INFO mapreduce.Job:  map 29% reduce 0%
18/07/27 18:21:43 INFO mapreduce.Job:  map 31% reduce 0%
18/07/27 18:21:44 INFO mapreduce.Job:  map 32% reduce 0%
18/07/27 18:21:45 INFO mapreduce.Job:  map 33% reduce 0%
18/07/27 18:21:46 INFO mapreduce.Job:  map 35% reduce 0%
18/07/27 18:21:50 INFO mapreduce.Job:  map 37% reduce 0%
18/07/27 18:21:51 INFO mapreduce.Job:  map 40% reduce 0%
18/07/27 18:21:52 INFO mapreduce.Job:  map 41% reduce 0%
18/07/27 18:21:54 INFO mapreduce.Job:  map 42% reduce 0%
18/07/27 18:21:55 INFO mapreduce.Job:  map 44% reduce 0%
18/07/27 18:21:56 INFO mapreduce.Job:  map 45% reduce 0%
18/07/27 18:21:58 INFO mapreduce.Job:  map 47% reduce 0%
18/07/27 18:21:59 INFO mapreduce.Job:  map 48% reduce 0%
18/07/27 18:22:00 INFO mapreduce.Job:  map 51% reduce 0%
18/07/27 18:22:01 INFO mapreduce.Job:  map 52% reduce 0%
18/07/27 18:22:03 INFO mapreduce.Job:  map 53% reduce 0%
18/07/27 18:22:06 INFO mapreduce.Job:  map 55% reduce 0%
18/07/27 18:22:07 INFO mapreduce.Job:  map 58% reduce 0%
18/07/27 18:22:08 INFO mapreduce.Job:  map 59% reduce 0%
18/07/27 18:22:10 INFO mapreduce.Job:  map 62% reduce 0%
18/07/27 18:22:11 INFO mapreduce.Job:  map 63% reduce 0%
18/07/27 18:22:15 INFO mapreduce.Job:  map 65% reduce 0%
18/07/27 18:22:16 INFO mapreduce.Job:  map 68% reduce 0%
18/07/27 18:22:17 INFO mapreduce.Job:  map 69% reduce 0%
18/07/27 18:22:19 INFO mapreduce.Job:  map 72% reduce 0%
18/07/27 18:22:20 INFO mapreduce.Job:  map 73% reduce 0%
18/07/27 18:22:23 INFO mapreduce.Job:  map 76% reduce 0%
18/07/27 18:22:24 INFO mapreduce.Job:  map 77% reduce 0%
18/07/27 18:22:26 INFO mapreduce.Job:  map 79% reduce 0%
18/07/27 18:22:27 INFO mapreduce.Job:  map 80% reduce 0%
18/07/27 18:22:28 INFO mapreduce.Job:  map 83% reduce 0%
18/07/27 18:22:29 INFO mapreduce.Job:  map 84% reduce 0%
18/07/27 18:22:31 INFO mapreduce.Job:  map 86% reduce 0%
18/07/27 18:22:32 INFO mapreduce.Job:  map 88% reduce 0%
18/07/27 18:22:35 INFO mapreduce.Job:  map 90% reduce 0%
18/07/27 18:22:36 INFO mapreduce.Job:  map 92% reduce 0%
18/07/27 18:22:37 INFO mapreduce.Job:  map 95% reduce 0%
18/07/27 18:22:39 INFO mapreduce.Job:  map 96% reduce 0%
18/07/27 18:22:41 INFO mapreduce.Job:  map 96% reduce 4%
18/07/27 18:22:42 INFO mapreduce.Job:  map 97% reduce 4%
18/07/27 18:22:43 INFO mapreduce.Job:  map 99% reduce 8%
18/07/27 18:22:44 INFO mapreduce.Job:  map 99% reduce 9%
18/07/27 18:22:45 INFO mapreduce.Job:  map 100% reduce 9%
18/07/27 18:22:46 INFO mapreduce.Job:  map 100% reduce 15%
18/07/27 18:22:47 INFO mapreduce.Job:  map 100% reduce 20%
18/07/27 18:22:48 INFO mapreduce.Job:  map 100% reduce 21%
18/07/27 18:22:49 INFO mapreduce.Job:  map 100% reduce 28%
18/07/27 18:22:50 INFO mapreduce.Job:  map 100% reduce 32%
18/07/27 18:22:51 INFO mapreduce.Job:  map 100% reduce 37%
18/07/27 18:22:52 INFO mapreduce.Job:  map 100% reduce 49%
18/07/27 18:22:53 INFO mapreduce.Job:  map 100% reduce 52%
18/07/27 18:22:54 INFO mapreduce.Job:  map 100% reduce 54%
18/07/27 18:22:55 INFO mapreduce.Job:  map 100% reduce 58%
18/07/27 18:22:56 INFO mapreduce.Job:  map 100% reduce 70%
18/07/27 18:22:57 INFO mapreduce.Job:  map 100% reduce 72%
18/07/27 18:22:58 INFO mapreduce.Job:  map 100% reduce 81%
18/07/27 18:22:59 INFO mapreduce.Job:  map 100% reduce 85%
18/07/27 18:23:01 INFO mapreduce.Job:  map 100% reduce 88%
18/07/27 18:23:02 INFO mapreduce.Job:  map 100% reduce 90%
18/07/27 18:23:04 INFO mapreduce.Job:  map 100% reduce 92%
18/07/27 18:23:05 INFO mapreduce.Job:  map 100% reduce 94%
18/07/27 18:23:07 INFO mapreduce.Job:  map 100% reduce 96%
18/07/27 18:23:08 INFO mapreduce.Job:  map 100% reduce 98%
18/07/27 18:23:10 INFO mapreduce.Job:  map 100% reduce 100%
18/07/27 18:23:11 INFO mapreduce.Job: Job job_1532715543477_0001 completed successfully
18/07/27 18:23:12 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=2912772853
                FILE: Number of bytes written=5778609654
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=6553617992
                HDFS: Number of bytes written=6553600000
                HDFS: Number of read operations=330
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters
                Launched map tasks=104
                Launched reduce tasks=6
                Data-local map tasks=104
                Total time spent by all maps in occupied slots (ms)=843673
                Total time spent by all reduces in occupied slots (ms)=172947
                Total time spent by all map tasks (ms)=843673
                Total time spent by all reduce tasks (ms)=172947
                Total vcore-seconds taken by all map tasks=843673
                Total vcore-seconds taken by all reduce tasks=172947
                Total megabyte-seconds taken by all map tasks=863921152
                Total megabyte-seconds taken by all reduce tasks=177097728
        Map-Reduce Framework
                Map input records=65536000
                Map output records=65536000
                Map output bytes=6684672000
                Map output materialized bytes=2851955313
                Input split bytes=17992
                Combine input records=0
                Combine output records=0
                Reduce input groups=65536000
                Reduce shuffle bytes=2851955313
                Reduce input records=65536000
                Reduce output records=65536000
                Spilled Records=131072000
                Shuffled Maps =624
                Failed Shuffles=0
                Merged Map outputs=624
                GC time elapsed (ms)=15207
                CPU time spent (ms)=539010
                Physical memory (bytes) snapshot=62434181120
                Virtual memory (bytes) snapshot=173505134592
                Total committed heap usage (bytes)=63450382336
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=6553600000
        File Output Format Counters
                Bytes Written=6553600000
18/07/27 18:23:12 INFO terasort.TeraSort: done


<time>
real    2m16.353s
user    0m6.506s
sys     0m0.318s
```