# 1,2,3.Maria db installation on Master node05 and Replica node03
```
[root@node05 ~]#yum install -y mariadb mariadb-server

[root@node05 ~]#systemctl start mariadb
[root@node05 ~]#systemctl enable mariadb

[root@node05 ~]# systemctl status mariadb
● mariadb.service - MariaDB database server
   Loaded: loaded (/usr/lib/systemd/system/mariadb.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2019-02-11 13:49:14 UTC; 11s ago
 Main PID: 31491 (mysqld_safe)
   CGroup: /system.slice/mariadb.service
           ├─31491 /bin/sh /usr/bin/mysqld_safe --basedir=/usr
           └─31654 /usr/libexec/mysqld --basedir=/usr --datadir=/var/lib/mysql --plugin-dir=/usr/lib64/mysql/plugin --log-error=/var/log/mariadb/mariad...
```

Install Mariadb connector on all nodes

```
[root@node05 ~]# yum install mysql-connector-java.noarch
```

# 4. Execute mysql_secure_installation

I have executed the script on both nodes node05 and node03

[root@node05 ~]# /usr/bin/mysql_secure_installation
```
NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none):
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

Set root password? [Y/n] Y
New password:
Re-enter new password:
Password updated successfully!
Reloading privilege tables..
 ... Success!


By default, a MariaDB installation has an anonymous user, allowing anyone
to log into MariaDB without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.

Remove anonymous users? [Y/n] Y
 ... Success!

Normally, root should only be allowed to connect from 'node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] Y
 ... Success!

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] Y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] Y
 ... Success!

Cleaning up...

All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!
[root@node05 ~]#
```

Then , I have restarted the mariadb service
```
[root@node05 ~]# systemctl restart mariadb
```

# 5.On the master MySQL node, grant replication privileges for your replica node

The node03 is my mariadb replica server.


on node05 (the master), I have added the rows below to the /etc/my.cnf
```
# New parameters 
innodb_file_per_table=1 
innodb_buffer_pool_size=1G 
innodb_flush_log_at_trx_commit=2 
innodb_flush_method=O_DIRECT
log_bin=mysql-bin 
binlog_format=ROW 
server_id=10 
innodb_support_xa=1
expire_logs_days = 1

```

Then , I have restared the mariadb service

Below, the istruction to creare the replica user and check the master status
```
[root@node05 ~]# mysql -u root -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 2
Server version: 5.5.60-MariaDB MariaDB Server

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> GRANT REPLICATION SLAVE ON *.* TO 'repl'@'node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'password123';
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> FLUSH TABLES WITH READ LOCK;
Query OK, 0 rows affected (0.00 sec)

MariaDB [(none)]> SHOW MASTER STATUS;
+------------------+----------+--------------+------------------+
| File             | Position | Binlog_Do_DB | Binlog_Ignore_DB |
+------------------+----------+--------------+------------------+
| mysql-bin.000001 |      245 |              |                  |
+------------------+----------+--------------+------------------+
1 row in set (0.00 sec)
```

To be sure about the databases alignement , I have done a dump of the master and imported it into slave

```
[root@node05 ~]# mysqldump --single-transaction --all-databases --master-data=1 --host=localhost > /tmp/hadoopMYSQL.out -p
Enter password:
[root@node05 ~]# scp /tmp/hadoopMYSQL.out diego@node03:/tmp/
Password:
hadoopMYSQL.out                                                                                                         100%  503KB  65.9MB/s   00:00
[root@node05 ~]# ssh diego@node03
Password:
[diego@node03 ~]$ sudo mysql -u root -p </tmp/hadoopMYSQL.out
[sudo] password for diego:
Enter password:
[diego@node03 ~]$
```

On Replica server, I have added the following rows to /etc/my.cnf
```
# New parameters 
innodb_file_per_table=1 
innodb_buffer_pool_size=4G 
innodb_flush_log_at_trx_commit=2 
innodb_flush_method=O_DIRECT
log_bin = mysql-bin 
binlog_format = ROW 
server_id = 11 
relay_log = mysql-relay-bin 
log_slave_updates = 1 
read_only = 1
expire_logs_days = 1

```

I have restarted mariadb service on Replica.

I have enabled and started the slave replica.

With show slave status I have checked the alignment with master
```
MariaDB [(none)]> flush slave;
MariaDB [(none)]> reset slave;
MariaDB [(none)]> CHANGE MASTER TO MASTER_HOST='node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net', MASTER_USER='repl',MASTER_PASSWORD='password123', MASTER_LOG_FILE='mysql-bin.000001', MASTER_LOG_POS=245;
MariaDB [(none)]> start slave;
MariaDB [(none)]> show slave status;
```

Create mysql user 
```
create database scm CHARACTER SET utf8;
create database amon CHARACTER SET utf8;
create database rman CHARACTER SET utf8;
create database metastore CHARACTER SET utf8;
create database sentry CHARACTER SET utf8;
create database nav CHARACTER SET utf8;
create database navms CHARACTER SET utf8;
create database oozie CHARACTER SET utf8; 
create database hue CHARACTER SET utf8;

grant all on scm.* TO 'scm'@'node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'scm';
grant all on amon.* TO 'amon'@'node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'amon';
grant all on rman.* TO 'rman'@'node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'rman';
grant all on metastore.* TO 'hive'@'node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'hive';
grant all on sentry.* TO 'sentry'@'node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'sentry';
grant all on nav.* TO 'nav'@'node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'nav';
grant all on navms.* TO 'navms'@'node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'navms';
grant all on oozie.* TO 'oozie'@'node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'oozie';
grant all on hue.* TO 'hue'@'node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'hue';

grant all on scm.* TO 'scm'@'node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'scm';
grant all on amon.* TO 'amon'@'node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'amon';
grant all on rman.* TO 'rman'@'node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'rman';
grant all on metastore.* TO 'hive'@'node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'hive';
grant all on sentry.* TO 'sentry'@'node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'sentry';
grant all on nav.* TO 'nav'@'node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'nav';
grant all on navms.* TO 'navms'@'node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'navms';
grant all on oozie.* TO 'oozie'@'node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'oozie';
grant all on hue.* TO 'hue'@'node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net' IDENTIFIED BY 'hue';
```

I have checked that on the replica server the new databases and the new users are present.







