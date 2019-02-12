# HDFS HA
Using Cloudera Manager, I have executed the wizard to enable high availability for the HDFS service.

During the wizard , I have set :

.  the name of the node where installing the stand-by namenode

.  the name of the three nodes where installing the Jounal service and the related folder 

After the end of the wizard , I have done the following manual configurations :

1.  Configure Hive service to use HDFS High Availability 

  I have stoped the Hive service.

  I have done a backup of the metastore 
  ```
  mysqldump -u hive -h node05 -p  metastore > /data/metastore.dmp
  ```
  from Cloudera manager I have executed "Actions > Update Hive Metastore NameNodes"

  then , I have restarted the hive service

2.  Configure Hue service to use HDFS High Availability 

   In Cloudera Manager , I have added the HttpFS instance to HDFS service.
   
   In Cloudera Manager , under the Hue configuration page, for property "HDFS Web Interface Role"  I have set HttpFS
   
   Then , I have restarted Hue

# DISTCP
to allow the copy from a cluster installed on Azure to a cluster installed on AWS we have:
1  .Added to hosts file of every Azure node the public ip address of the AWS cluster node with the private name
```
54.93.59.233 sebc-edge.internal sebc-edge
18.184.154.32 sebc-server1.internal sebc-server1
3.122.228.233 sebc-worker1.internal sebc-worker1
35.159.46.176 sebc-server2.internal sebc-server2
3.120.26.248 sebc-worker2.internal sebc-worker2
```
2  .Opened the port 50070 and 50075 of AWS for inbound communication to any ( this because the current Azure configuration has dynamic ip configuration for outbound)

Then, we have successfully executed a copy of a small file. We have used hdfs because this user is present in both clusters
```
export HADOOP_USER_NAME=hdfs
hadoop distcp /tmp/prova.txt webhdfs://ec2-18-184-154-32.eu-central-1.compute.amazonaws.com/tmp/
```
This is the result of target cluster
```
[root@sebc-edge mysql-connector-java-5.1.47]# hdfs dfs -ls /tmp/
Found 6 items
d---------   - hdfs   supergroup          0 2019-02-12 16:22 /tmp/.cloudera_health_monitoring_canary_files
drwxr-xr-x   - hdfs   supergroup          0 2019-02-12 16:06 /tmp/dist
drwx-wx-wx   - hive   supergroup          0 2019-02-12 12:52 /tmp/hive
drwxrwxrwt   - mapred hadoop              0 2019-02-12 12:51 /tmp/logs
-rw-r--r--   3 hdfs   supergroup         18 2019-02-12 16:23 /tmp/prova.txt
-rw-r--r--   3 root   supergroup         20 2019-02-12 15:48 /tmp/test.txt

[root@sebc-edge mysql-connector-java-5.1.47]# hdfs dfs -cat /tmp/prova.txt
test trasmissione
```
