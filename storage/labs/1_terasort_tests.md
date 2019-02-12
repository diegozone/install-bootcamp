I have created an ad-hoc user for this test and on HDFS I have created its home directory
```
[root@node05 ~]# export HADOOP_USER_NAME=hdfs
[root@node05 ~]# hadoop fs -mkdir /user/testuser
[root@node05 ~]# hadoop fs -chown testuser:testuser /user/testuser
[root@node05 ~]# hadoop fs -ls /user
Found 5 items
drwxrwxrwx   - mapred   hadoop            0 2019-02-11 18:58 /user/history
drwxrwxr-t   - hive     hive              0 2019-02-11 18:59 /user/hive
drwxrwxr-x   - hue      hue               0 2019-02-11 18:59 /user/hue
drwxrwxr-x   - oozie    oozie             0 2019-02-11 18:59 /user/oozie
drwxr-xr-x   - testuser testuser          0 2019-02-12 14:01 /user/testuser
```

Then, I have executed the teragen example several time with different settings
```
export HADOOP_USER_NAME=testuser
[root@node05 /]# time hadoop jar hadoop-examples.jar teragen -Dmapred.map.tasks=4 -Dmapred.map.tasks.speculative.execution=false 1000000000 /tmp/terasort-input

real    0m27.485s
user    0m7.636s
sys     0m0.549s


[root@node05 /]# time hadoop jar hadoop-examples.jar teragen -Dmapred.map.tasks=8 -Dmapred.map.tasks.speculative.execution=false 1000000000 /tmp/terasort-input
real    0m23.438s
user    0m7.562s
sys     0m0.532s

[root@node05 /]# time hadoop jar hadoop-examples.jar teragen -Dmapred.map.tasks=12 -Dmapred.map.tasks.speculative.execution=false 1000000000 /tmp/terasort-input
real    0m28.408s
user    0m8.119s
sys     0m0.535s
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
