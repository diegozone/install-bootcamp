```
[root@gateway ~]# export HADOOP_USER_NAME=rocky
[root@gateway ~]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=8 -Dmapreduce.map.memory.mb=768 12345000 /user/rocky/tgen
19/02/15 10:06:29 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
19/02/15 10:06:29 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
19/02/15 10:06:29 INFO terasort.TeraGen: Generating 12345000 using 1
19/02/15 10:06:29 INFO mapreduce.JobSubmitter: number of splits:1
19/02/15 10:06:29 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local693381911_0001
19/02/15 10:06:30 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
19/02/15 10:06:30 INFO mapreduce.Job: Running job: job_local693381911_0001
19/02/15 10:06:30 INFO mapred.LocalJobRunner: OutputCommitter set in config null
19/02/15 10:06:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
19/02/15 10:06:30 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
19/02/15 10:06:30 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
19/02/15 10:06:30 INFO mapred.LocalJobRunner: Waiting for map tasks
19/02/15 10:06:30 INFO mapred.LocalJobRunner: Starting task: attempt_local693381911_0001_m_000000_0
19/02/15 10:06:30 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
19/02/15 10:06:30 INFO output.FileOutputCommitter: FileOutputCommitter skip cleanup _temporary folders under output directory:false, ignore cleanup failures: false
19/02/15 10:06:30 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
19/02/15 10:06:30 INFO mapred.MapTask: Processing split: org.apache.hadoop.examples.terasort.TeraGen$RangeInputFormat$RangeInputSplit@4b9629d2
19/02/15 10:06:31 INFO mapreduce.Job: Job job_local693381911_0001 running in uber mode : false
19/02/15 10:06:31 INFO mapreduce.Job:  map 0% reduce 0%
19/02/15 10:06:42 INFO mapred.LocalJobRunner: map > map
19/02/15 10:06:43 INFO mapreduce.Job:  map 82% reduce 0%
19/02/15 10:06:44 INFO mapred.LocalJobRunner: map > map
19/02/15 10:06:44 INFO mapred.Task: Task:attempt_local693381911_0001_m_000000_0 is done. And is in the process of committing
19/02/15 10:06:44 INFO mapred.LocalJobRunner: map > map
19/02/15 10:06:44 INFO mapred.Task: Task attempt_local693381911_0001_m_000000_0 is allowed to commit now
19/02/15 10:06:44 INFO output.FileOutputCommitter: Saved output of task 'attempt_local693381911_0001_m_000000_0' to hdfs://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:8020/user/rocky/tgen/_temporary/0/task_local693381911_0001_m_000000
19/02/15 10:06:44 INFO mapred.LocalJobRunner: map
19/02/15 10:06:44 INFO mapred.Task: Task 'attempt_local693381911_0001_m_000000_0' done.
19/02/15 10:06:44 INFO mapred.LocalJobRunner: Finishing task: attempt_local693381911_0001_m_000000_0
19/02/15 10:06:44 INFO mapred.LocalJobRunner: map task executor complete.
19/02/15 10:06:45 INFO mapreduce.Job:  map 100% reduce 0%
19/02/15 10:06:45 INFO mapreduce.Job: Job job_local693381911_0001 completed successfully
19/02/15 10:06:45 INFO mapreduce.Job: Counters: 21
        File System Counters
                FILE: Number of bytes read=276514
                FILE: Number of bytes written=619326
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=0
                HDFS: Number of bytes written=1234500000
                HDFS: Number of read operations=4
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Map-Reduce Framework
                Map input records=12345000
                Map output records=12345000
                Input split bytes=82
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=87
                Total committed heap usage (bytes)=188219392
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=26510014434051487
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=1234500000

real    0m18.108s
user    0m24.656s
sys     0m2.505s
```
