```
[rocky@master ~]$ kinit rocky
Password for rocky@DIEGOZONE.ABC:
[rocky@master ~]$ time hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort /user/rocky/tgen /user/rocky/tsort
19/02/15 10:52:56 INFO terasort.TeraSort: starting
19/02/15 10:52:57 INFO hdfs.DFSClient: Created token for rocky: HDFS_DELEGATION_TOKEN owner=rocky@DIEGOZONE.ABC, renewer=yarn, realUser=, issueDate=1550227977369, maxDate=1550832777369, sequenceNumber=4, masterKeyId=2 on 10.0.1.5:8020
19/02/15 10:52:57 INFO security.TokenCache: Got dt for hdfs://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.1.5:8020, Ident: (token for rocky: HDFS_DELEGATION_TOKEN owner=rocky@DIEGOZONE.ABC, renewer=yarn, realUser=, issueDate=1550227977369, maxDate=1550832777369, sequenceNumber=4, masterKeyId=2)
19/02/15 10:52:57 INFO input.FileInputFormat: Total input paths to process : 8
Spent 346ms computing base-splits.
Spent 2ms computing TeraScheduler splits.
Computing input splits took 349ms
Sampling 10 splits of 16
Making 6 from 100000 sampled records
Computing parititions took 631ms
Spent 982ms computing partitions.
19/02/15 10:52:58 INFO client.RMProxy: Connecting to ResourceManager at master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net/10.0.1.5:8032
19/02/15 10:52:58 INFO mapreduce.JobSubmitter: number of splits:16
19/02/15 10:52:58 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1550227239263_0004
19/02/15 10:52:58 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 10.0.1.5:8020, Ident: (token for rocky: HDFS_DELEGATION_TOKEN owner=rocky@DIEGOZONE.ABC, renewer=yarn, realUser=, issueDate=1550227977369, maxDate=1550832777369, sequenceNumber=4, masterKeyId=2)
19/02/15 10:52:59 INFO impl.YarnClientImpl: Submitted application application_1550227239263_0004
19/02/15 10:52:59 INFO mapreduce.Job: The url to track the job: http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:8088/proxy/application_1550227239263_0004/
19/02/15 10:52:59 INFO mapreduce.Job: Running job: job_1550227239263_0004
19/02/15 10:53:01 INFO mapreduce.Job: Job job_1550227239263_0004 running in uber mode : false
19/02/15 10:53:01 INFO mapreduce.Job:  map 0% reduce 0%
19/02/15 10:53:01 INFO mapreduce.Job: Job job_1550227239263_0004 failed with state FAILED due to: Application application_1550227239263_0004 failed 2 times due to AM Container for appattempt_1550227239263_0004_000002 exited with  exitCode: -1000
For more detailed output, check application tracking page:http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:8088/proxy/application_1550227239263_0004/Then, click on links to logs of each attempt.
Diagnostics: Application application_1550227239263_0004 initialization failed (exitCode=255) with output: main : command provided 0
main : run as user is rocky
main : requested yarn user is rocky
Can't create directory /data/yarn/nm/usercache/rocky/appcache/application_1550227239263_0004 - Permission denied
Can't create directory /mnt/resource/yarn/nm/usercache/rocky/appcache/application_1550227239263_0004 - Permission denied
Did not create any app directories

Failing this attempt. Failing the application.
19/02/15 10:53:01 INFO mapreduce.Job: Counters: 0
19/02/15 10:53:01 INFO terasort.TeraSort: done

real    0m6.301s
user    0m8.533s
sys     0m0.488s
```
