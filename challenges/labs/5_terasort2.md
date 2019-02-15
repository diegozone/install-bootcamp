```
[root@master ~]# kinit rocky1
Password for rocky1@DIEGOZONE.ABC:
[root@master ~]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/rocky1/tgen /user/rocky1/tsort
19/02/15 11:56:41 INFO terasort.TeraSort: starting
19/02/15 11:56:43 INFO hdfs.DFSClient: Created token for rocky1: HDFS_DELEGATION_TOKEN owner=rocky1@DIEGOZONE.ABC, renewer=yarn, realUser=, issueDate=1550231802992, maxDate=1550836602992, sequenceNumber=12, masterKeyId=2 on 10.0.1.5:8020
19/02/15 11:56:43 INFO security.TokenCache: Got dt for hdfs://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.1.5:8020, Ident: (token for rocky1: HDFS_DELEGATION_TOKEN owner=rocky1@DIEGOZONE.ABC, renewer=yarn, realUser=, issueDate=1550231802992, maxDate=1550836602992, sequenceNumber=12, masterKeyId=2)
19/02/15 11:56:43 INFO input.FileInputFormat: Total input paths to process : 8
Spent 356ms computing base-splits.
Spent 3ms computing TeraScheduler splits.
Computing input splits took 360ms
Sampling 10 splits of 16
Making 6 from 100000 sampled records
Computing parititions took 673ms
Spent 1034ms computing partitions.
19/02/15 11:56:43 INFO client.RMProxy: Connecting to ResourceManager at master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net/10.0.1.5:8032
19/02/15 11:56:44 INFO mapreduce.JobSubmitter: number of splits:16
19/02/15 11:56:44 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1550227239263_0008
19/02/15 11:56:44 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.1.5:8020, Ident: (token for rocky1: HDFS_DELEGATION_TOKEN owner=rocky1@DIEGOZONE.ABC, renewer=yarn, realUser=, issueDate=1550231802992, maxDate=1550836602992, sequenceNumber=12, masterKeyId=2)
19/02/15 11:56:44 INFO impl.YarnClientImpl: Submitted application application_1550227239263_0008
19/02/15 11:56:44 INFO mapreduce.Job: The url to track the job: http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:8088/proxy/application_1550227239263_0008/
19/02/15 11:56:44 INFO mapreduce.Job: Running job: job_1550227239263_0008
19/02/15 11:56:53 INFO mapreduce.Job: Job job_1550227239263_0008 running in uber mode : false
19/02/15 11:56:53 INFO mapreduce.Job:  map 0% reduce 0%
19/02/15 11:57:04 INFO mapreduce.Job:  map 6% reduce 0%
19/02/15 11:57:09 INFO mapreduce.Job:  map 19% reduce 0%
19/02/15 11:57:10 INFO mapreduce.Job:  map 31% reduce 0%
19/02/15 11:57:11 INFO mapreduce.Job:  map 38% reduce 0%
19/02/15 11:57:15 INFO mapreduce.Job:  map 50% reduce 0%
19/02/15 11:57:16 INFO mapreduce.Job:  map 81% reduce 0%
19/02/15 11:57:17 INFO mapreduce.Job:  map 100% reduce 0%
19/02/15 11:57:27 INFO mapreduce.Job:  map 100% reduce 50%
19/02/15 11:57:28 INFO mapreduce.Job:  map 100% reduce 100%
19/02/15 11:57:29 INFO mapreduce.Job: Job job_1550227239263_0008 completed successfully
19/02/15 11:57:29 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=542763086
                FILE: Number of bytes written=1085047769
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=1234502640
                HDFS: Number of bytes written=1234500000
                HDFS: Number of read operations=66
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters
                Launched map tasks=16
                Launched reduce tasks=6
                Data-local map tasks=16
                Total time spent by all maps in occupied slots (ms)=218712
                Total time spent by all reduces in occupied slots (ms)=59237
                Total time spent by all map tasks (ms)=218712
                Total time spent by all reduce tasks (ms)=59237
                Total vcore-milliseconds taken by all map tasks=218712
                Total vcore-milliseconds taken by all reduce tasks=59237
                Total megabyte-milliseconds taken by all map tasks=223961088
                Total megabyte-milliseconds taken by all reduce tasks=60658688
        Map-Reduce Framework
                Map input records=12345000
                Map output records=12345000
                Map output bytes=1259190000
                Map output materialized bytes=538932643
                Input split bytes=2640
                Combine input records=0
                Combine output records=0
                Reduce input groups=12345000
                Reduce shuffle bytes=538932643
                Reduce input records=12345000
                Reduce output records=12345000
                Spilled Records=24690000
                Shuffled Maps =96
                Failed Shuffles=0
                Merged Map outputs=96
                GC time elapsed (ms)=6045
                CPU time spent (ms)=154560
                Physical memory (bytes) snapshot=12219281408
                Virtual memory (bytes) snapshot=61520723968
                Total committed heap usage (bytes)=12629049344
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=1234500000
        File Output Format Counters
                Bytes Written=1234500000
19/02/15 11:57:29 INFO terasort.TeraSort: done

real    0m49.421s
user    0m9.101s
sys     0m0.556s
```
