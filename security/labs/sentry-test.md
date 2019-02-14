Before setting the Sentry permissions
```
[diegozone@node05 ~]$ kinit -p diegozone@BOOTCAMP.COM
Password for diegozone@BOOTCAMP.COM:
[diegozone@node05 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.15.1 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net@BOOTCAMP.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net@BOOTCAMP.COM
Connected to: Apache Hive (version 1.1.0-cdh5.15.1)
Driver: Hive JDBC (version 1.1.0-cdh5.15.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20190214090404_4f3ce900-a83c-42af-b3e8-5095c2831cd8): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20190214090404_4f3ce900-a83c-42af-b3e8-5095c2831cd8); Time taken: 0.288 seconds
INFO  : Executing command(queryId=hive_20190214090404_4f3ce900-a83c-42af-b3e8-5095c2831cd8): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20190214090404_4f3ce900-a83c-42af-b3e8-5095c2831cd8); Time taken: 0.297 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (1.916 seconds)
0: jdbc:hive2://localhost:10000/default>
```
George permissions
```
[diegozone@node05 ~]$ kinit george
Password for george@BOOTCAMP.COM:
[diegozone@node05 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.15.1 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net@BOOTCAMP.COM;
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net@BOOTCAMP.COM;
Connected to: Apache Hive (version 1.1.0-cdh5.15.1)
Driver: Hive JDBC (version 1.1.0-cdh5.15.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20190214091818_b4c547fe-5b1d-4618-b0de-d8773942a090): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20190214091818_b4c547fe-5b1d-4618-b0de-d8773942a090); Time taken: 0.09 seconds
INFO  : Executing command(queryId=hive_20190214091818_b4c547fe-5b1d-4618-b0de-d8773942a090): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20190214091818_b4c547fe-5b1d-4618-b0de-d8773942a090); Time taken: 0.286 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.505 seconds)
0: jdbc:hive2://localhost:10000/default>
```
ferdinand permissions
```
[diegozone@node05 ~]$ kinit ferdinand
Password for ferdinand@BOOTCAMP.COM:
[diegozone@node05 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.15.1 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net@BOOTCAMP.COM;
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net@BOOTCAMP.COM;
Connected to: Apache Hive (version 1.1.0-cdh5.15.1)
Driver: Hive JDBC (version 1.1.0-cdh5.15.1)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20190214092121_adec5652-fb8e-4879-aed8-ba7121bdd9b5): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20190214092121_adec5652-fb8e-4879-aed8-ba7121bdd9b5); Time taken: 0.081 seconds
INFO  : Executing command(queryId=hive_20190214092121_adec5652-fb8e-4879-aed8-ba7121bdd9b5): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20190214092121_adec5652-fb8e-4879-aed8-ba7121bdd9b5); Time taken: 0.33 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.516 seconds)
0: jdbc:hive2://localhost:10000/default>
```
