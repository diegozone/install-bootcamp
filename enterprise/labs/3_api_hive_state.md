```
[diegozone@node05 ~]$ curl -X POST -u diegozone:cloudera http://localhost:7180/api/v19/clusters/diegozone/services/hive/commands/stop
{
  "id" : 1521,
  "name" : "Stop",
  "startTime" : "2019-02-14T12:53:48.835Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}[diegozone@node05 ~]$ curl -X POST -u diegozone:cloudera http://localhost:7180/api/v19/clusters/diegozone/services/hive/commands/start
{
  "id" : 1527,
  "name" : "Start",
  "startTime" : "2019-02-14T12:55:13.161Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}[diegozone@node05 ~]$ curl -u diegozone:cloudera http://localhost:7180/api/v19/clusters/diegozone/services/hive
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}[diegozone@node05 ~]$
```
