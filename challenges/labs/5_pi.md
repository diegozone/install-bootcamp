```
[denali@master ~]$ kinit denali
Password for denali@DIEGOZONE.ABC:
[denali@master ~]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar pi 50 100
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
19/02/15 10:55:54 INFO client.RMProxy: Connecting to ResourceManager at master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net/10.0.1.5:8032
19/02/15 10:55:54 INFO hdfs.DFSClient: Created token for denali: HDFS_DELEGATION_TOKEN owner=denali@DIEGOZONE.ABC, renewer=yarn, realUser=, issueDate=1550228154531, maxDate=1550832954531, sequenceNumber=5, masterKeyId=2 on 10.0.1.5:8020
19/02/15 10:55:54 INFO security.TokenCache: Got dt for hdfs://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.1.5:8020, Ident: (token for denali: HDFS_DELEGATION_TOKEN owner=denali@DIEGOZONE.ABC, renewer=yarn, realUser=, issueDate=1550228154531, maxDate=1550832954531, sequenceNumber=5, masterKeyId=2)
19/02/15 10:55:54 INFO input.FileInputFormat: Total input paths to process : 50
19/02/15 10:55:54 INFO mapreduce.JobSubmitter: number of splits:50
19/02/15 10:55:54 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1550227239263_0005
19/02/15 10:55:54 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.1.5:8020, Ident: (token for denali: HDFS_DELEGATION_TOKEN owner=denali@DIEGOZONE.ABC, renewer=yarn, realUser=, issueDate=1550228154531, maxDate=1550832954531, sequenceNumber=5, masterKeyId=2)
19/02/15 10:55:55 INFO impl.YarnClientImpl: Submitted application application_1550227239263_0005
19/02/15 10:55:55 INFO mapreduce.Job: The url to track the job: http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:8088/proxy/application_1550227239263_0005/
19/02/15 10:55:55 INFO mapreduce.Job: Running job: job_1550227239263_0005
19/02/15 10:56:04 INFO mapreduce.Job: Job job_1550227239263_0005 running in uber mode : false
19/02/15 10:56:04 INFO mapreduce.Job:  map 0% reduce 0%
19/02/15 10:56:12 INFO mapreduce.Job:  map 4% reduce 0%
19/02/15 10:56:13 INFO mapreduce.Job:  map 6% reduce 0%
19/02/15 10:56:19 INFO mapreduce.Job:  map 22% reduce 0%
19/02/15 10:56:20 INFO mapreduce.Job:  map 28% reduce 0%
19/02/15 10:56:24 INFO mapreduce.Job:  map 30% reduce 0%
19/02/15 10:56:27 INFO mapreduce.Job:  map 38% reduce 0%
19/02/15 10:56:28 INFO mapreduce.Job:  map 40% reduce 0%
19/02/15 10:56:29 INFO mapreduce.Job:  map 46% reduce 0%
19/02/15 10:56:30 INFO mapreduce.Job:  map 50% reduce 0%
19/02/15 10:56:31 INFO mapreduce.Job:  map 52% reduce 0%
19/02/15 10:56:33 INFO mapreduce.Job:  map 56% reduce 0%
19/02/15 10:56:35 INFO mapreduce.Job:  map 60% reduce 0%
19/02/15 10:56:36 INFO mapreduce.Job:  map 64% reduce 0%
19/02/15 10:56:37 INFO mapreduce.Job:  map 66% reduce 0%
19/02/15 10:56:38 INFO mapreduce.Job:  map 68% reduce 0%
19/02/15 10:56:39 INFO mapreduce.Job:  map 78% reduce 0%
19/02/15 10:56:41 INFO mapreduce.Job:  map 80% reduce 0%
19/02/15 10:56:43 INFO mapreduce.Job:  map 86% reduce 0%
19/02/15 10:56:44 INFO mapreduce.Job:  map 88% reduce 0%
19/02/15 10:56:45 INFO mapreduce.Job:  map 92% reduce 0%
19/02/15 10:56:47 INFO mapreduce.Job:  map 94% reduce 0%
19/02/15 10:56:48 INFO mapreduce.Job:  map 100% reduce 0%
19/02/15 10:56:49 INFO mapreduce.Job:  map 100% reduce 100%
19/02/15 10:56:49 INFO mapreduce.Job: Job job_1550227239263_0005 completed successfully
19/02/15 10:56:49 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=263
                FILE: Number of bytes written=7728856
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=15840
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=203
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters
                Launched map tasks=50
                Launched reduce tasks=1
                Data-local map tasks=50
                Total time spent by all maps in occupied slots (ms)=356651
                Total time spent by all reduces in occupied slots (ms)=4761
                Total time spent by all map tasks (ms)=356651
                Total time spent by all reduce tasks (ms)=4761
                Total vcore-milliseconds taken by all map tasks=356651
                Total vcore-milliseconds taken by all reduce tasks=4761
                Total megabyte-milliseconds taken by all map tasks=365210624
                Total megabyte-milliseconds taken by all reduce tasks=4875264
        Map-Reduce Framework
                Map input records=50
                Map output records=100
                Map output bytes=900
                Map output materialized bytes=1700
                Input split bytes=9940
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
                GC time elapsed (ms)=9118
                CPU time spent (ms)=43230
                Physical memory (bytes) snapshot=23726514176
                Virtual memory (bytes) snapshot=142284750848
                Total committed heap usage (bytes)=25390219264
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
Job Finished in 55.175 seconds
Estimated value of Pi is 3.14160000000000000000

```
