I have executed the commands below to create the precious folder and copy on it the SEBC-master.zip file
```
[root@node05 ~]# export HADOOP_USER_NAME=hdfs
[root@node05 ~]# hadoop fs -mkdir /precious
[root@node05 ~]# hadoop fs -put SEBC-master.zip /precious
[root@node05 ~]# hadoop fs -ls /precious
Found 1 items
-rw-r--r--   3 hdfs supergroup     765921 2019-02-12 20:09 /precious/SEBC-master.zip
```
Using command line tool , but it's possible also with Cloudera manager, I have enabled the snapshot on the folder precious and created the snapshot sebc-hdfs-test 
```
[root@node05 ~]# hdfs dfsadmin -allowSnapshot /precious
Allowing snaphot on /precious succeeded
[root@node05 ~]# hdfs dfs -createSnapshot /precious sebc-hdfs-test
Created snapshot /precious/.snapshot/sebc-hdfs-test
[root@node05 ~]#
```

I have removed the zip file inside the precious folder . It's not possible remove a snapshottable folder with a snapshot.
Then , I have restored the snapshot
```
[root@node05 ~]# hadoop fs -rm /precious/SEBC-master.zip
19/02/12 20:26:28 INFO fs.TrashPolicyDefault: Moved: 'hdfs://hdfsHA/precious/SEBC-master.zip' to trash at: hdfs://hdfsHA/user/hdfs/.Trash/Current/precious/SEBC-master.zip
[root@node05 ~]# hadoop fs -rmdir /precious
rmdir: The directory /precious cannot be deleted since /precious is snapshottable and already has snapshots

[root@node05 ~]#  hadoop fs -ls /precious/.snapshot/sebc-hdfs-test
Found 1 items
-rw-r--r--   3 hdfs supergroup     765921 2019-02-12 20:09 /precious/.snapshot/sebc-hdfs-test/SEBC-master.zip

[root@node05 ~]# hadoop fs -cp -ptopax /precious/.snapshot/sebc-hdfs-test/* /precious
[root@node05 ~]# hadoop fs -ls /precious/
Found 1 items
-rw-r--r--   3 hdfs supergroup     765921 2019-02-12 20:09 /precious/SEBC-master.zip
```
