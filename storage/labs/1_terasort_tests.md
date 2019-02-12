I have created an ad-hoc user for this test and on HDFS I have created its home directory
```
[root@node05 ~]# export HADOOP_USER_NAME=hdfs
[root@node05 ~]# hadoop fs -mkdir /user/diegozone
[root@node05 ~]# hadoop fs -chown diegozone:diegozone /user/diegozone
[root@node05 ~]# hadoop fs -ls /user
Found 7 items
drwxr-xr-x   - diegozone diegozone           0 2019-02-12 16:36 /user/diegozone
drwx------   - hdfs      supergroup          0 2019-02-12 15:45 /user/hdfs
drwxrwxrwx   - mapred    hadoop              0 2019-02-11 18:58 /user/history
drwxrwxr-t   - hive      hive                0 2019-02-11 18:59 /user/hive
drwxrwxr-x   - hue       hue                 0 2019-02-11 18:59 /user/hue
drwxrwxr-x   - oozie     oozie               0 2019-02-11 18:59 /user/oozie

```

Then, I have executed the teragen example with the settings specified in the exercise.
```
[root@node05 ~]# export HADOOP_USER_NAME=diegozone
[root@node05 ~]# time hadoop jar hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=32M  -Dmapred.map.tasks.speculative.execution=false 100000000 /user/diegozone/terasort-input

real    3m27.469s
user    0m8.763s
sys     0m0.762s

[root@node05 ~]# hadoop fs -du -h /user/diegozone                                                                                        0      0       /user/diegozone/.Trash
0      0       /user/diegozone/.staging
9.3 G  27.9 G  /user/diegozone/terasort-input

```

then , I test cluster with terasort
```
[root@node05 /]# time hadoop  jar hadoop-examples.jar terasort -Dmapred.map.tasks=8 -Dmapred.reduce.tasks=8 -Dmapred.reduce.tasks.speculative.execution=false /user/diegozone/terasort-input /user/diegozone/terasort-output
real    5m47.520s
user    0m11.115s
sys     0m0.832s

0      0       /user/diegozone/.Trash
0      0       /user/diegozone/.staging
9.3 G  27.9 G  /user/diegozone/terasort-input
9.3 G  9.3 G   /user/diegozone/terasort-output

```
The terasort-output folder is under replication of the blocks.
Infact,the "HDFS \chart libraries \ blocks and files" highlights a big number of blocks not replicated . 
