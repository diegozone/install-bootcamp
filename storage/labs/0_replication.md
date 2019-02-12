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
