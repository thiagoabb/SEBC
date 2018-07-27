#Challenge 5: PI test
```
time hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi 50 100

<output>
[root@cloudera-2 hue]# kinit caldecott
Password for caldecott@THIAGOABB.SFO:
[root@cloudera-2 hue]#
[root@cloudera-2 hue]#
[root@cloudera-2 hue]#
[root@cloudera-2 hue]# time hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi 50 100
Number of Maps  = 50
Samples per Map = 100
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Wrote input for Map #10
Wrote input for Map #11
Wrote input for Map #12
Wrote input for Map #13
Wrote input for Map #14
Wrote input for Map #15
Wrote input for Map #16
Wrote input for Map #17
Wrote input for Map #18
Wrote input for Map #19
Wrote input for Map #20
Wrote input for Map #21
Wrote input for Map #22
Wrote input for Map #23
Wrote input for Map #24
Wrote input for Map #25
Wrote input for Map #26
Wrote input for Map #27
Wrote input for Map #28
Wrote input for Map #29
Wrote input for Map #30
Wrote input for Map #31
Wrote input for Map #32
Wrote input for Map #33
Wrote input for Map #34
Wrote input for Map #35
Wrote input for Map #36
Wrote input for Map #37
Wrote input for Map #38
Wrote input for Map #39
Wrote input for Map #40
Wrote input for Map #41
Wrote input for Map #42
Wrote input for Map #43
Wrote input for Map #44
Wrote input for Map #45
Wrote input for Map #46
Wrote input for Map #47
Wrote input for Map #48
Wrote input for Map #49
Starting Job
18/07/27 18:28:11 INFO client.RMProxy: Connecting to ResourceManager at cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net/10.0.1.5:8032
18/07/27 18:28:11 INFO hdfs.DFSClient: Created token for caldecott: HDFS_DELEGATION_TOKEN owner=caldecott@THIAGOABB.SFO, renewer=yarn, realUser=, issueDate=1532716091354, maxDate=1533320891354, sequenceNumber=2, masterKeyId=2 on 10.0.1.5:8020
18/07/27 18:28:11 INFO security.TokenCache: Got dt for hdfs://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.1.5:8020, Ident: (token for caldecott: HDFS_DELEGATION_TOKEN owner=caldecott@THIAGOABB.SFO, renewer=yarn, realUser=, issueDate=1532716091354, maxDate=1533320891354, sequenceNumber=2, masterKeyId=2)
18/07/27 18:28:11 INFO input.FileInputFormat: Total input paths to process : 50
18/07/27 18:28:11 INFO mapreduce.JobSubmitter: number of splits:50
18/07/27 18:28:12 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1532715543477_0002
18/07/27 18:28:12 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.1.5:8020, Ident: (token for caldecott: HDFS_DELEGATION_TOKEN owner=caldecott@THIAGOABB.SFO, renewer=yarn, realUser=, issueDate=1532716091354, maxDate=1533320891354, sequenceNumber=2, masterKeyId=2)
18/07/27 18:28:12 INFO impl.YarnClientImpl: Submitted application application_1532715543477_0002
18/07/27 18:28:12 INFO mapreduce.Job: The url to track the job: http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:8088/proxy/application_1532715543477_0002/
18/07/27 18:28:12 INFO mapreduce.Job: Running job: job_1532715543477_0002
18/07/27 18:28:20 INFO mapreduce.Job: Job job_1532715543477_0002 running in uber mode : false
18/07/27 18:28:20 INFO mapreduce.Job:  map 0% reduce 0%
18/07/27 18:28:26 INFO mapreduce.Job:  map 4% reduce 0%
18/07/27 18:28:27 INFO mapreduce.Job:  map 6% reduce 0%
18/07/27 18:28:31 INFO mapreduce.Job:  map 24% reduce 0%
18/07/27 18:28:32 INFO mapreduce.Job:  map 26% reduce 0%
18/07/27 18:28:34 INFO mapreduce.Job:  map 28% reduce 0%
18/07/27 18:28:37 INFO mapreduce.Job:  map 30% reduce 0%
18/07/27 18:28:38 INFO mapreduce.Job:  map 40% reduce 0%
18/07/27 18:28:39 INFO mapreduce.Job:  map 50% reduce 0%
18/07/27 18:28:41 INFO mapreduce.Job:  map 52% reduce 0%
18/07/27 18:28:44 INFO mapreduce.Job:  map 64% reduce 0%
18/07/27 18:28:45 INFO mapreduce.Job:  map 72% reduce 0%
18/07/27 18:28:47 INFO mapreduce.Job:  map 74% reduce 0%
18/07/27 18:28:49 INFO mapreduce.Job:  map 78% reduce 0%
18/07/27 18:28:50 INFO mapreduce.Job:  map 86% reduce 0%
18/07/27 18:28:51 INFO mapreduce.Job:  map 94% reduce 0%
18/07/27 18:28:52 INFO mapreduce.Job:  map 96% reduce 0%
18/07/27 18:28:54 INFO mapreduce.Job:  map 100% reduce 0%
18/07/27 18:28:56 INFO mapreduce.Job:  map 100% reduce 100%
18/07/27 18:28:56 INFO mapreduce.Job: Job job_1532715543477_0002 completed successfully
18/07/27 18:28:56 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=259
                FILE: Number of bytes written=6396681
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=16140
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=203
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters
                Launched map tasks=50
                Launched reduce tasks=1
                Data-local map tasks=50
                Total time spent by all maps in occupied slots (ms)=265695
                Total time spent by all reduces in occupied slots (ms)=3723
                Total time spent by all map tasks (ms)=265695
                Total time spent by all reduce tasks (ms)=3723
                Total vcore-seconds taken by all map tasks=265695
                Total vcore-seconds taken by all reduce tasks=3723
                Total megabyte-seconds taken by all map tasks=272071680
                Total megabyte-seconds taken by all reduce tasks=3812352
        Map-Reduce Framework
                Map input records=50
                Map output records=100
                Map output bytes=900
                Map output materialized bytes=1700
                Input split bytes=10240
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=1700
                Reduce input records=100
                Reduce output records=0
                Spilled Records=200
                Shuffled Maps =50
                Failed Shuffles=0
                Merged Map outputs=50
                GC time elapsed (ms)=1679
                CPU time spent (ms)=29650
                Physical memory (bytes) snapshot=25626271744
                Virtual memory (bytes) snapshot=80504389632
                Total committed heap usage (bytes)=25776095232
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=5900
        File Output Format Counters
                Bytes Written=97
Job Finished in 45.396 seconds
Estimated value of Pi is 3.14160000000000000000

real    0m49.050s
user    0m5.375s
sys     0m0.298s
```