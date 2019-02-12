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
export HADOOP_USER_NAME=diegozone
time hadoop jar hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Ddfs.block.size=32M  -Dmapred.map.tasks.speculative.execution=false 1000000000 /user/diegozone/terasort-input

real    31m39.237s
user    0m14.309s
sys     0m2.029s

[root@node05 ~]# hadoop fs -du -h /user/diegozone
0       0        /user/diegozone/.Trash
0       0        /user/diegozone/.staging
93.1 G  279.4 G  /user/diegozone/terasort-input


```

then , I test cluster with terasort
```
[root@node05 /]# time hadoop  jar hadoop-examples.jar terasort -Dmapred.map.tasks=4 -Dmapred.reduce.tasks=4 -Dmapred.reduce.tasks.speculative.execution=false /tmp/terasort-input /tmp/terasort-output
real    0m44.440s
user    0m9.663s
sys     0m0.591s

[root@node05 /]# time hadoop  jar hadoop-examples.jar terasort -Dmapred.map.tasks=8 -Dmapred.reduce.tasks=8 -Dmapred.reduce.tasks.speculative.execution=false /tmp/terasort-input /tmp/terasort-output
real    0m40.786s
user    0m9.052s
sys     0m0.562s

[root@node05 /]# time hadoop  jar hadoop-examples.jar terasort -Dmapred.map.tasks=12 -Dmapred.reduce.tasks=12 -Dmapred.reduce.tasks.speculative.execution=false /tmp/terasort-input /tmp/terasort-output
real    0m44.175s
user    0m9.568s
sys     0m0.565s
```

The conclusion is that , in case of dedicated cluster,for current configuration the best choise is to set 2 mapper and 2 reducer per worker (At the end I have 4 workers)
