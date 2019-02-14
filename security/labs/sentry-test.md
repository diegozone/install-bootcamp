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
