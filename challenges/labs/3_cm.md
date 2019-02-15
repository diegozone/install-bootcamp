* The command and output for `hdfs dfs -ls /user`
```
[hdfs@gateway ~]$ hadoop fs -ls /user
Found 7 items
drwxr-xr-x   - denali alaska            0 2019-02-15 09:43 /user/denali
drwxrwxrwx   - mapred hadoop            0 2019-02-15 09:40 /user/history
drwxrwxr-t   - hive   hive              0 2019-02-15 09:40 /user/hive
drwxrwxr-x   - hue    hue               0 2019-02-15 09:41 /user/hue
drwxrwxr-x   - impala impala            0 2019-02-15 09:43 /user/impala
drwxrwxr-x   - oozie  oozie             0 2019-02-15 09:41 /user/oozie
drwxr-xr-x   - rocky  colorado          0 2019-02-15 09:43 /user/rocky
```
* The command and output from the CM API call `../api/v14/hosts`
```
{
    "items": [
        {
            "hostId": "b511135b-8712-441b-9ae7-6d1bd7db9faf",
            "ipAddress": "10.0.1.4",
            "hostname": "gateway.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net",
            "rackId": "/default",
            "hostUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/hostRedirect/b511135b-8712-441b-9ae7-6d1bd7db9faf",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "commissionState": "COMMISSIONED",
            "numCores": 4,
            "numPhysicalCores": 2,
            "totalPhysMemBytes": 16808796160
        },
        {
            "hostId": "98ecfc19-2d1e-41fd-9242-5895deb0c6c7",
            "ipAddress": "10.0.1.5",
            "hostname": "master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net",
            "rackId": "/default",
            "hostUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/hostRedirect/98ecfc19-2d1e-41fd-9242-5895deb0c6c7",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "commissionState": "COMMISSIONED",
            "numCores": 4,
            "numPhysicalCores": 2,
            "totalPhysMemBytes": 16808796160
        },
        {
            "hostId": "c3fb19d0-cccf-4d69-a607-1466a4302bfa",
            "ipAddress": "10.0.1.6",
            "hostname": "worker01.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net",
            "rackId": "/default",
            "hostUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/hostRedirect/c3fb19d0-cccf-4d69-a607-1466a4302bfa",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "commissionState": "COMMISSIONED",
            "numCores": 4,
            "numPhysicalCores": 2,
            "totalPhysMemBytes": 16808796160
        },
        {
            "hostId": "f25ceaea-4751-431d-a292-6b49c2504f7d",
            "ipAddress": "10.0.1.7",
            "hostname": "worker02.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net",
            "rackId": "/default",
            "hostUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/hostRedirect/f25ceaea-4751-431d-a292-6b49c2504f7d",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "commissionState": "COMMISSIONED",
            "numCores": 4,
            "numPhysicalCores": 2,
            "totalPhysMemBytes": 16808796160
        },
        {
            "hostId": "61942a3f-8abe-41e9-8b71-adf448e52b87",
            "ipAddress": "10.0.1.8",
            "hostname": "worker03.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net",
            "rackId": "/default",
            "hostUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/hostRedirect/61942a3f-8abe-41e9-8b71-adf448e52b87",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "commissionState": "COMMISSIONED",
            "numCores": 4,
            "numPhysicalCores": 2,
            "totalPhysMemBytes": 16808796160
        }

    ]
}
```
* The command and output from the CM API call `../api/v8/clusters/<githubName>/services`
```
{
    "items": [
        {
            "name": "zookeeper",
            "type": "ZOOKEEPER",
            "clusterRef": {
                "clusterName": "cluster"
            },
            "serviceUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/serviceRedirect/zookeeper",
            "serviceState": "STARTED",
            "healthSummary": "GOOD",
            "healthChecks": [
                {
                    "name": "ZOOKEEPER_CANARY_HEALTH",
                    "summary": "GOOD"
                },
                {
                    "name": "ZOOKEEPER_SERVERS_HEALTHY",
                    "summary": "GOOD"
                }
            ],
            "configStalenessStatus": "FRESH",
            "clientConfigStalenessStatus": "FRESH",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "displayName": "ZooKeeper"
        },
        {
            "name": "oozie",
            "type": "OOZIE",
            "clusterRef": {
                "clusterName": "cluster"
            },
            "serviceUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/serviceRedirect/oozie",
            "serviceState": "STARTED",
            "healthSummary": "GOOD",
            "healthChecks": [
                {
                    "name": "OOZIE_OOZIE_SERVERS_HEALTHY",
                    "summary": "GOOD"
                }
            ],
            "configStalenessStatus": "FRESH",
            "clientConfigStalenessStatus": "FRESH",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "displayName": "Oozie"
        },
        {
            "name": "hue",
            "type": "HUE",
            "clusterRef": {
                "clusterName": "cluster"
            },
            "serviceUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/serviceRedirect/hue",
            "serviceState": "STARTED",
            "healthSummary": "GOOD",
            "healthChecks": [
                {
                    "name": "HUE_HUE_SERVERS_HEALTHY",
                    "summary": "GOOD"
                },
                {
                    "name": "HUE_LOAD_BALANCER_HEALTHY",
                    "summary": "GOOD"
                }
            ],
            "configStalenessStatus": "FRESH",
            "clientConfigStalenessStatus": "FRESH",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "displayName": "Hue"
        },
        {
            "name": "hdfs",
            "type": "HDFS",
            "clusterRef": {
                "clusterName": "cluster"
            },
            "serviceUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/serviceRedirect/hdfs",
            "serviceState": "STARTED",
            "healthSummary": "GOOD",
            "healthChecks": [
                {
                    "name": "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
                    "summary": "GOOD"
                },
                {
                    "name": "HDFS_CANARY_HEALTH",
                    "summary": "GOOD"
                },
                {
                    "name": "HDFS_DATA_NODES_HEALTHY",
                    "summary": "GOOD"
                },
                {
                    "name": "HDFS_FREE_SPACE_REMAINING",
                    "summary": "GOOD"
                },
                {
                    "name": "HDFS_HA_NAMENODE_HEALTH",
                    "summary": "GOOD"
                },
                {
                    "name": "HDFS_MISSING_BLOCKS",
                    "summary": "GOOD"
                },
                {
                    "name": "HDFS_UNDER_REPLICATED_BLOCKS",
                    "summary": "GOOD"
                }
            ],
            "configStalenessStatus": "FRESH",
            "clientConfigStalenessStatus": "FRESH",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "displayName": "HDFS"
        },
        {
            "name": "yarn",
            "type": "YARN",
            "clusterRef": {
                "clusterName": "cluster"
            },
            "serviceUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/serviceRedirect/yarn",
            "serviceState": "STARTED",
            "healthSummary": "GOOD",
            "healthChecks": [
                {
                    "name": "YARN_JOBHISTORY_HEALTH",
                    "summary": "GOOD"
                },
                {
                    "name": "YARN_NODE_MANAGERS_HEALTHY",
                    "summary": "GOOD"
                },
                {
                    "name": "YARN_RESOURCEMANAGERS_HEALTH",
                    "summary": "GOOD"
                },
                {
                    "name": "YARN_USAGE_AGGREGATION_HEALTH",
                    "summary": "DISABLED"
                }
            ],
            "configStalenessStatus": "FRESH",
            "clientConfigStalenessStatus": "FRESH",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "displayName": "YARN (MR2 Included)"
        },
        {
            "name": "hive",
            "type": "HIVE",
            "clusterRef": {
                "clusterName": "cluster"
            },
            "serviceUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/serviceRedirect/hive",
            "serviceState": "STARTED",
            "healthSummary": "GOOD",
            "healthChecks": [
                {
                    "name": "HIVE_HIVEMETASTORES_HEALTHY",
                    "summary": "GOOD"
                },
                {
                    "name": "HIVE_HIVESERVER2S_HEALTHY",
                    "summary": "GOOD"
                }
            ],
            "configStalenessStatus": "FRESH",
            "clientConfigStalenessStatus": "FRESH",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "displayName": "Hive"
        },
        {
            "name": "impala",
            "type": "IMPALA",
            "clusterRef": {
                "clusterName": "cluster"
            },
            "serviceUrl": "http://master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net:7180/cmf/serviceRedirect/impala",
            "serviceState": "STARTED",
            "healthSummary": "GOOD",
            "healthChecks": [
                {
                    "name": "IMPALA_ASSIGNMENT_LOCALITY",
                    "summary": "DISABLED"
                },
                {
                    "name": "IMPALA_CATALOGSERVER_HEALTH",
                    "summary": "GOOD"
                },
                {
                    "name": "IMPALA_IMPALADS_HEALTHY",
                    "summary": "GOOD"
                },
                {
                    "name": "IMPALA_STATESTORE_HEALTH",
                    "summary": "GOOD"
                }
            ],
            "configStalenessStatus": "FRESH",
            "clientConfigStalenessStatus": "FRESH",
            "maintenanceMode": false,
            "maintenanceOwners": [],
            "displayName": "Impala"
        }
    ]
}
```

