*The full teragen command and output
```
[root@master ~]# export HADOOP_USER_NAME=rocky
[root@master ~]# time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.map.tasks=8 -Dmapreduce.job.maps=8 -D mapreduce.map.memory.mb=768 12345000 /user/rocky/tgen
19/02/15 10:20:57 INFO client.RMProxy: Connecting to ResourceManager at master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net/10.0.1.5:8032
19/02/15 10:20:58 INFO terasort.TeraGen: Generating 12345000 using 8
19/02/15 10:20:58 INFO mapreduce.JobSubmitter: number of splits:8
19/02/15 10:20:58 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1550224016172_0001
19/02/15 10:20:59 INFO impl.YarnClientImpl: Submitted application application_1550224016172_0001
19/02/15 10:20:59 INFO mapreduce.Job: The url to track the job: http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:8088/proxy/application_1550224016172_0001/
19/02/15 10:20:59 INFO mapreduce.Job: Running job: job_1550224016172_0001
19/02/15 10:21:06 INFO mapreduce.Job: Job job_1550224016172_0001 running in uber mode : false
19/02/15 10:21:06 INFO mapreduce.Job:  map 0% reduce 0%
19/02/15 10:21:15 INFO mapreduce.Job:  map 13% reduce 0%
19/02/15 10:21:17 INFO mapreduce.Job:  map 25% reduce 0%
19/02/15 10:21:19 INFO mapreduce.Job:  map 38% reduce 0%
19/02/15 10:21:20 INFO mapreduce.Job:  map 88% reduce 0%
19/02/15 10:21:21 INFO mapreduce.Job:  map 100% reduce 0%
19/02/15 10:21:21 INFO mapreduce.Job: Job job_1550224016172_0001 completed successfully
19/02/15 10:21:21 INFO mapreduce.Job: Counters: 31
        File System Counters
                FILE: Number of bytes read=0
                FILE: Number of bytes written=1200144
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=677
                HDFS: Number of bytes written=1234500000
                HDFS: Number of read operations=32
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=16
        Job Counters
                Launched map tasks=8
                Other local map tasks=8
                Total time spent by all maps in occupied slots (ms)=86655
                Total time spent by all reduces in occupied slots (ms)=0
                Total time spent by all map tasks (ms)=86655
                Total vcore-milliseconds taken by all map tasks=86655
                Total megabyte-milliseconds taken by all map tasks=88734720
        Map-Reduce Framework
                Map input records=12345000
                Map output records=12345000
                Input split bytes=677
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=1727
                CPU time spent (ms)=37400
                Physical memory (bytes) snapshot=2371985408
                Virtual memory (bytes) snapshot=20522106880
                Total committed heap usage (bytes)=2318401536
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=26510014434051487
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=1234500000
```
* The result of the time command
```
real    0m26.521s
user    0m7.224s
sys     0m0.432s
```
* The command and output of `hdfs dfs -ls /user/rocky/tgen`
```
[root@master ~]# hadoop fs -ls /user/rocky/tgen
Found 9 items
-rw-r--r--   3 rocky colorado          0 2019-02-15 10:21 /user/rocky/tgen/_SUCCESS
-rw-r--r--   3 rocky colorado  154312500 2019-02-15 10:21 /user/rocky/tgen/part-m-00000
-rw-r--r--   3 rocky colorado  154312500 2019-02-15 10:21 /user/rocky/tgen/part-m-00001
-rw-r--r--   3 rocky colorado  154312500 2019-02-15 10:21 /user/rocky/tgen/part-m-00002
-rw-r--r--   3 rocky colorado  154312500 2019-02-15 10:21 /user/rocky/tgen/part-m-00003
-rw-r--r--   3 rocky colorado  154312500 2019-02-15 10:21 /user/rocky/tgen/part-m-00004
-rw-r--r--   3 rocky colorado  154312500 2019-02-15 10:21 /user/rocky/tgen/part-m-00005
-rw-r--r--   3 rocky colorado  154312500 2019-02-15 10:21 /user/rocky/tgen/part-m-00006
-rw-r--r--   3 rocky colorado  154312500 2019-02-15 10:21 /user/rocky/tgen/part-m-00007
```
* The command and output of `hadoop fsck -blocks /user/rocky`
```
[root@master ~]# hadoop fsck -blocks /user/rocky
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:50070/fsck?ugi=rocky&blocks=1&path=%2Fuser%2Frocky
FSCK started by rocky (auth:SIMPLE) from /10.0.1.5 for path /user/rocky at Fri Feb 15 10:23:55 UTC 2019
.................Status: HEALTHY
 Total size:    6172500000 B
 Total dirs:    11
 Total files:   17
 Total symlinks:                0
 Total blocks (validated):      56 (avg. block size 110223214 B)
 Minimally replicated blocks:   56 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Fri Feb 15 10:23:55 UTC 2019 in 4 milliseconds


The filesystem under path '/user/rocky' is HEALTHY

```
