# Configure the repository

on node05 , I have installed the repository 
```
[root@node05 /]# wget https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo -P /etc/yum.repos.d/
--2019-02-11 16:05:38--  https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo
Resolving archive.cloudera.com (archive.cloudera.com)... 151.101.36.167
Connecting to archive.cloudera.com (archive.cloudera.com)|151.101.36.167|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 290 [binary/octet-stream]
Saving to: ‘/etc/yum.repos.d/cloudera-manager.repo’

100%[================================================================================================================>] 290         --.-K/s   in 0s

2019-02-11 16:05:38 (33.7 MB/s) - ‘/etc/yum.repos.d/cloudera-manager.repo’ saved [290/290]

[root@node05 /]# cat /etc/yum.repos.d/cloudera-manager.repo
[cloudera-manager]
# Packages for Cloudera Manager, Version 5, on RedHat or CentOS 7 x86_64
name=Cloudera Manager
baseurl=https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5/
gpgkey =https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera
gpgcheck = 1
```
then, I have imported the the repository signing GPG key
```
[root@node05 /]# rpm --import https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera
```


# Install a supported Oracle JDK on your first node

first of all , I have removed all existing jdk in my nodes 

```
[root@node05 ~]# yum list installed | grep jdk
java-1.8.0-openjdk.x86_64                   1:1.8.0.191.b12-1.el7_6    updates
java-1.8.0-openjdk-headless.x86_64
[root@node05 ~]# yum remove java-1.8.0-openjdk.x86_64
[root@node05 ~]# yum remove java-1.8.0-openjdk-headless.x86_64
[root@node05 ~]# java -version
-bash: /bin/java: No such file or directory
```

then , I have installed the jdk-8u201-linux-x64.rpm on the all nodes
```
[root@node05 ~]# yum install /tmp/jdk-8u201-linux-x64.rpm
[root@node05 ~]# java -version
java version "1.8.0_201"
Java(TM) SE Runtime Environment (build 1.8.0_201-b09)
Java HotSpot(TM) 64-Bit Server VM (build 25.201-b09, mixed mode)
```

# Install a supported JDBC connector on all nodes 

Install Mariadb connector on all nodes

```
[root@node05 ~]# yum install mysql-connector-java.noarch
```

# Create the databases and access grants you will need

I have laready created all users in mysql configuration exercise.

# Configure Cloudera Manager to connect to the database

I have installed on master the cloudera manager server
```
yum install cloudera-manager-daemons cloudera-manager-server
[root@node05 /]# /usr/share/cmf/schema/scm_prepare_database.sh -h node05 mysql scm scm scm
JAVA_HOME=/usr/java/jdk1.8.0_201-amd64
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.8.0_201-amd64/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/java/postgresql-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
```

# Start your Cloudera Manager server

I have executed the following command to set up the cloudera manager server and make it bootable
```
[root@node05 /]# service cloudera-scm-server start
Starting cloudera-scm-server (via systemctl):              [  OK  ]
[root@node05 /]# chkconfig cloudera-scm-server on
[root@node05 /]#
```

the Cloudera manager console url is http://node05:7180

from outside Azure, it's necessary to use an ssh tunnel
