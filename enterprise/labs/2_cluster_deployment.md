Below, the output of the command 

curl -u diegozone:cloudera http://localhost:7180/api/v19/cm/deployment

```
{
    "timestamp": "2019-02-14T12:31:17.826Z",
    "clusters": [
        {
            "name": "diegozone",
            "version": "CDH5",
            "services": [
                {
                    "name": "zookeeper",
                    "type": "ZOOKEEPER",
                    "config": {
                        "roleTypeConfigs": [],
                        "items": [
                            {
                                "name": "enableSecurity",
                                "value": "true"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "zookeeper-SERVER-061dbb38888a8734039a66c0e2b4e502",
                            "type": "SERVER",
                            "hostRef": {
                                "hostId": "5eac8760-36e1-48dc-b3a4-4669a6b4beec"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "e4icvxkq4ecgsqgqonhvsztu2"
                                    },
                                    {
                                        "name": "serverId",
                                        "value": "3"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "zookeeper-SERVER-63fef2965a4ccd083e20e3d86d4c6cc4",
                            "type": "SERVER",
                            "hostRef": {
                                "hostId": "c5b9804d-f59b-402f-9f44-29f091c38879"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "5rqk7lb7m3gnyst9ry7z1y0ec"
                                    },
                                    {
                                        "name": "serverId",
                                        "value": "2"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "zookeeper-SERVER-99e8666d2e96d77eeeae2e791b4f5adb",
                            "type": "SERVER",
                            "hostRef": {
                                "hostId": "98a7cb3a-ecab-4f7a-946e-4f6695cac73e"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "6u5mwsaqw6kj6p06b87ske7xy"
                                    },
                                    {
                                        "name": "serverId",
                                        "value": "1"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "ZooKeeper"
                },
                {
                    "name": "hdfs",
                    "type": "HDFS",
                    "config": {
                        "roleTypeConfigs": [
                            {
                                "roleType": "BALANCER",
                                "items": [
                                    {
                                        "name": "balancer_java_heapsize",
                                        "value": "915406848"
                                    }
                                ]
                            },
                            {
                                "roleType": "DATANODE",
                                "items": [
                                    {
                                        "name": "dfs_data_dir_list",
                                        "value": "/data/dfs/dn,/mnt/resource/dfs/dn"
                                    },
                                    {
                                        "name": "dfs_datanode_data_dir_perm",
                                        "value": "700"
                                    },
                                    {
                                        "name": "dfs_datanode_failed_volumes_tolerated",
                                        "value": "1"
                                    },
                                    {
                                        "name": "dfs_datanode_http_port",
                                        "value": "1006"
                                    },
                                    {
                                        "name": "dfs_datanode_port",
                                        "value": "1004"
                                    }
                                ]
                            },
                            {
                                "roleType": "GATEWAY",
                                "items": [
                                    {
                                        "name": "dfs_client_use_trash",
                                        "value": "true"
                                    }
                                ]
                            },
                            {
                                "roleType": "JOURNALNODE",
                                "items": [
                                    {
                                        "name": "dfs_journalnode_edits_dir",
                                        "value": "/data/journal/"
                                    }
                                ]
                            },
                            {
                                "roleType": "NAMENODE",
                                "items": [
                                    {
                                        "name": "dfs_name_dir_list",
                                        "value": "/data/dfs/nn,/mnt/resource/dfs/nn"
                                    },
                                    {
                                        "name": "dfs_namenode_servicerpc_address",
                                        "value": "8022"
                                    }
                                ]
                            },
                            {
                                "roleType": "SECONDARYNAMENODE",
                                "items": [
                                    {
                                        "name": "fs_checkpoint_dir_list",
                                        "value": "/data/dfs/snn"
                                    },
                                    {
                                        "name": "secondary_namenode_java_heapsize",
                                        "value": "915406848"
                                    }
                                ]
                            }
                        ],
                        "items": [
                            {
                                "name": "dfs_encrypt_data_transfer_algorithm",
                                "value": "AES/CTR/NoPadding"
                            },
                            {
                                "name": "dfs_ha_fencing_cloudera_manager_secret_key",
                                "value": "ZzALfVfnvfzyVU08ZxdR3Udt6V6c0Y"
                            },
                            {
                                "name": "fc_authorization_secret_key",
                                "value": "psaD06zYYuIw2Dhq1clZcQjUMiiiUc"
                            },
                            {
                                "name": "hadoop_secure_web_ui",
                                "value": "true"
                            },
                            {
                                "name": "hadoop_security_authentication",
                                "value": "kerberos"
                            },
                            {
                                "name": "hadoop_security_authorization",
                                "value": "true"
                            },
                            {
                                "name": "http_auth_signature_secret",
                                "value": "y7b4eqZW9782sQdUQw3W2eNXE4Uy9S"
                            },
                            {
                                "name": "rm_dirty",
                                "value": "true"
                            },
                            {
                                "name": "zookeeper_service",
                                "value": "zookeeper"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "hdfs-BALANCER-dc8c6a0c641fa6adf7137c6fe69c819e",
                            "type": "BALANCER",
                            "hostRef": {
                                "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hdfs-DATANODE-061dbb38888a8734039a66c0e2b4e502",
                            "type": "DATANODE",
                            "hostRef": {
                                "hostId": "5eac8760-36e1-48dc-b3a4-4669a6b4beec"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "3y3e4fb6znp1n3a45enfqipj0"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-DATANODE-63fef2965a4ccd083e20e3d86d4c6cc4",
                            "type": "DATANODE",
                            "hostRef": {
                                "hostId": "c5b9804d-f59b-402f-9f44-29f091c38879"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "4tej41i5pw4rfzq7s3mpndz35"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-DATANODE-99e8666d2e96d77eeeae2e791b4f5adb",
                            "type": "DATANODE",
                            "hostRef": {
                                "hostId": "98a7cb3a-ecab-4f7a-946e-4f6695cac73e"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "bchtebcriat9j3uu1kl72rw0q"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-DATANODE-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "DATANODE",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "626s0gdnmaaiam1uotrwjwspi"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-FAILOVERCONTROLLER-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "FAILOVERCONTROLLER",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "4unvodkxumso1htoelbjjbfry"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-FAILOVERCONTROLLER-dc8c6a0c641fa6adf7137c6fe69c819e",
                            "type": "FAILOVERCONTROLLER",
                            "hostRef": {
                                "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "2igt0a7nqtmcvxv352jly7gxx"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-HTTPFS-061dbb38888a8734039a66c0e2b4e502",
                            "type": "HTTPFS",
                            "hostRef": {
                                "hostId": "5eac8760-36e1-48dc-b3a4-4669a6b4beec"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "avv3wr80vhmwuo0553evx8601"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-JOURNALNODE-061dbb38888a8734039a66c0e2b4e502",
                            "type": "JOURNALNODE",
                            "hostRef": {
                                "hostId": "5eac8760-36e1-48dc-b3a4-4669a6b4beec"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "2ivu9zaxlm3be5vchukuk85oz"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-JOURNALNODE-63fef2965a4ccd083e20e3d86d4c6cc4",
                            "type": "JOURNALNODE",
                            "hostRef": {
                                "hostId": "c5b9804d-f59b-402f-9f44-29f091c38879"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "d2gmtuhwoh2s9nzupg5yqgjpx"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-JOURNALNODE-99e8666d2e96d77eeeae2e791b4f5adb",
                            "type": "JOURNALNODE",
                            "hostRef": {
                                "hostId": "98a7cb3a-ecab-4f7a-946e-4f6695cac73e"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "5uhcwvmfu2drgkjb2msmzy3az"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-NAMENODE-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "NAMENODE",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "autofailover_enabled",
                                        "value": "true"
                                    },
                                    {
                                        "name": "dfs_federation_namenode_nameservice",
                                        "value": "hdfsHA"
                                    },
                                    {
                                        "name": "dfs_namenode_quorum_journal_name",
                                        "value": "hdfsHA"
                                    },
                                    {
                                        "name": "namenode_id",
                                        "value": "111"
                                    },
                                    {
                                        "name": "role_jceks_password",
                                        "value": "8o8up0pu8z9rrh3bymssm05h6"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hdfs-NAMENODE-dc8c6a0c641fa6adf7137c6fe69c819e",
                            "type": "NAMENODE",
                            "hostRef": {
                                "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "autofailover_enabled",
                                        "value": "true"
                                    },
                                    {
                                        "name": "dfs_federation_namenode_nameservice",
                                        "value": "hdfsHA"
                                    },
                                    {
                                        "name": "dfs_namenode_quorum_journal_name",
                                        "value": "hdfsHA"
                                    },
                                    {
                                        "name": "namenode_id",
                                        "value": "76"
                                    },
                                    {
                                        "name": "role_jceks_password",
                                        "value": "3ycy4hnj1exye1vcupk88qujh"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "HDFS"
                },
                {
                    "name": "yarn",
                    "type": "YARN",
                    "config": {
                        "roleTypeConfigs": [
                            {
                                "roleType": "GATEWAY",
                                "items": [
                                    {
                                        "name": "mapred_reduce_tasks",
                                        "value": "8"
                                    },
                                    {
                                        "name": "mapred_submit_replication",
                                        "value": "3"
                                    }
                                ]
                            },
                            {
                                "roleType": "JOBHISTORY",
                                "items": [
                                    {
                                        "name": "mr2_jobhistory_java_heapsize",
                                        "value": "915406848"
                                    }
                                ]
                            },
                            {
                                "roleType": "NODEMANAGER",
                                "items": [
                                    {
                                        "name": "yarn_nodemanager_heartbeat_interval_ms",
                                        "value": "100"
                                    },
                                    {
                                        "name": "yarn_nodemanager_local_dirs",
                                        "value": "/data/yarn/nm,/mnt/resource/yarn/nm"
                                    },
                                    {
                                        "name": "yarn_nodemanager_log_dirs",
                                        "value": "/data/yarn/container-logs,/mnt/resource/yarn/container-logs"
                                    },
                                    {
                                        "name": "yarn_nodemanager_resource_cpu_vcores",
                                        "value": "4"
                                    },
                                    {
                                        "name": "yarn_nodemanager_resource_memory_mb",
                                        "value": "4734"
                                    }
                                ]
                            },
                            {
                                "roleType": "RESOURCEMANAGER",
                                "items": [
                                    {
                                        "name": "resource_manager_java_heapsize",
                                        "value": "915406848"
                                    },
                                    {
                                        "name": "yarn_scheduler_maximum_allocation_mb",
                                        "value": "4734"
                                    },
                                    {
                                        "name": "yarn_scheduler_maximum_allocation_vcores",
                                        "value": "4"
                                    }
                                ]
                            }
                        ],
                        "items": [
                            {
                                "name": "hadoop_secure_web_ui",
                                "value": "true"
                            },
                            {
                                "name": "hdfs_service",
                                "value": "hdfs"
                            },
                            {
                                "name": "rm_dirty",
                                "value": "true"
                            },
                            {
                                "name": "zk_authorization_secret_key",
                                "value": "nzAX1bl3krTJPjhtCcAnPZP6sCmhw8"
                            },
                            {
                                "name": "zookeeper_service",
                                "value": "zookeeper"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "yarn-JOBHISTORY-dc8c6a0c641fa6adf7137c6fe69c819e",
                            "type": "JOBHISTORY",
                            "hostRef": {
                                "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "6klav453l7p2i47rsbuctqgz4"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "yarn-NODEMANAGER-061dbb38888a8734039a66c0e2b4e502",
                            "type": "NODEMANAGER",
                            "hostRef": {
                                "hostId": "5eac8760-36e1-48dc-b3a4-4669a6b4beec"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "3n3n9ltzdyijc87s38cdtr9jj"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "yarn-NODEMANAGER-63fef2965a4ccd083e20e3d86d4c6cc4",
                            "type": "NODEMANAGER",
                            "hostRef": {
                                "hostId": "c5b9804d-f59b-402f-9f44-29f091c38879"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "2lzesccjvtvkfaa4i4vldg3na"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "yarn-NODEMANAGER-99e8666d2e96d77eeeae2e791b4f5adb",
                            "type": "NODEMANAGER",
                            "hostRef": {
                                "hostId": "98a7cb3a-ecab-4f7a-946e-4f6695cac73e"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "ej5dz8w8mq18it59ncxt3o031"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "yarn-NODEMANAGER-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "NODEMANAGER",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "2ho8y9nnij5ge7jn7chgz81f9"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "yarn-RESOURCEMANAGER-dc8c6a0c641fa6adf7137c6fe69c819e",
                            "type": "RESOURCEMANAGER",
                            "hostRef": {
                                "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "rm_id",
                                        "value": "83"
                                    },
                                    {
                                        "name": "role_jceks_password",
                                        "value": "2ru2bdrulrqw56muskq715qld"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "YARN (MR2 Included)"
                },
                {
                    "name": "hive",
                    "type": "HIVE",
                    "config": {
                        "roleTypeConfigs": [
                            {
                                "roleType": "HIVEMETASTORE",
                                "items": [
                                    {
                                        "name": "hive_enable_db_notification",
                                        "value": "true"
                                    },
                                    {
                                        "name": "hive_metastore_java_heapsize",
                                        "value": "2421161984"
                                    },
                                    {
                                        "name": "hive_metastore_server_max_message_size",
                                        "value": "242116198"
                                    }
                                ]
                            },
                            {
                                "roleType": "HIVESERVER2",
                                "items": [
                                    {
                                        "name": "hiveserver2_enable_impersonation",
                                        "value": "false"
                                    },
                                    {
                                        "name": "hiveserver2_java_heapsize",
                                        "value": "2421161984"
                                    },
                                    {
                                        "name": "hiveserver2_spark_driver_memory",
                                        "value": "966367641"
                                    },
                                    {
                                        "name": "hiveserver2_spark_executor_cores",
                                        "value": "4"
                                    },
                                    {
                                        "name": "hiveserver2_spark_executor_memory",
                                        "value": "1852991078"
                                    },
                                    {
                                        "name": "hiveserver2_spark_yarn_driver_memory_overhead",
                                        "value": "102"
                                    },
                                    {
                                        "name": "hiveserver2_spark_yarn_executor_memory_overhead",
                                        "value": "311"
                                    }
                                ]
                            }
                        ],
                        "items": [
                            {
                                "name": "hive_metastore_database_host",
                                "value": "node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net"
                            },
                            {
                                "name": "hive_metastore_database_password",
                                "value": "hive"
                            },
                            {
                                "name": "hive_proxy_user_groups_list",
                                "value": "hive,hue,sentry"
                            },
                            {
                                "name": "mapreduce_yarn_service",
                                "value": "yarn"
                            },
                            {
                                "name": "sentry_service",
                                "value": "sentry"
                            },
                            {
                                "name": "zookeeper_service",
                                "value": "zookeeper"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "hive-GATEWAY-061dbb38888a8734039a66c0e2b4e502",
                            "type": "GATEWAY",
                            "hostRef": {
                                "hostId": "5eac8760-36e1-48dc-b3a4-4669a6b4beec"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hive-GATEWAY-63fef2965a4ccd083e20e3d86d4c6cc4",
                            "type": "GATEWAY",
                            "hostRef": {
                                "hostId": "c5b9804d-f59b-402f-9f44-29f091c38879"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hive-GATEWAY-99e8666d2e96d77eeeae2e791b4f5adb",
                            "type": "GATEWAY",
                            "hostRef": {
                                "hostId": "98a7cb3a-ecab-4f7a-946e-4f6695cac73e"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hive-GATEWAY-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "GATEWAY",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hive-GATEWAY-dc8c6a0c641fa6adf7137c6fe69c819e",
                            "type": "GATEWAY",
                            "hostRef": {
                                "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "hive-HIVEMETASTORE-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "HIVEMETASTORE",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "3qafmz9qr2a3hz87vyveb48kt"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hive-HIVESERVER2-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "HIVESERVER2",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "1hmpei549g8jqvy9kv5r35qs4"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "Hive"
                },
                {
                    "name": "oozie",
                    "type": "OOZIE",
                    "config": {
                        "roleTypeConfigs": [
                            {
                                "roleType": "OOZIE_SERVER",
                                "items": [
                                    {
                                        "name": "oozie_database_host",
                                        "value": "node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net"
                                    },
                                    {
                                        "name": "oozie_database_password",
                                        "value": "oozie"
                                    },
                                    {
                                        "name": "oozie_database_type",
                                        "value": "mysql"
                                    },
                                    {
                                        "name": "oozie_database_user",
                                        "value": "oozie"
                                    },
                                    {
                                        "name": "oozie_java_heapsize",
                                        "value": "52428800"
                                    }
                                ]
                            }
                        ],
                        "items": [
                            {
                                "name": "hive_service",
                                "value": "hive"
                            },
                            {
                                "name": "mapreduce_yarn_service",
                                "value": "yarn"
                            },
                            {
                                "name": "zookeeper_service",
                                "value": "zookeeper"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "oozie-OOZIE_SERVER-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "OOZIE_SERVER",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "4a3yeoc31v04qmjsju4524j2g"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "Oozie"
                },
                {
                    "name": "hue",
                    "type": "HUE",
                    "config": {
                        "roleTypeConfigs": [],
                        "items": [
                            {
                                "name": "database_host",
                                "value": "node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net"
                            },
                            {
                                "name": "database_password",
                                "value": "hue"
                            },
                            {
                                "name": "database_type",
                                "value": "mysql"
                            },
                            {
                                "name": "hive_service",
                                "value": "hive"
                            },
                            {
                                "name": "hue_webhdfs",
                                "value": "hdfs-HTTPFS-061dbb38888a8734039a66c0e2b4e502"
                            },
                            {
                                "name": "impala_service",
                                "value": "impala"
                            },
                            {
                                "name": "oozie_service",
                                "value": "oozie"
                            },
                            {
                                "name": "sentry_service",
                                "value": "sentry"
                            },
                            {
                                "name": "zookeeper_service",
                                "value": "zookeeper"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "hue-HUE_LOAD_BALANCER-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "HUE_LOAD_BALANCER",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "8zlvk2wma4kmggcyfjtzuxpf4"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hue-HUE_SERVER-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "HUE_SERVER",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "navmetadataserver_cmdb_password",
                                        "value": "7efea9e8-ab39-4598-91be-e0a7be64a056"
                                    },
                                    {
                                        "name": "role_jceks_password",
                                        "value": "cci0mg50j6j14klizvc4e17tk"
                                    },
                                    {
                                        "name": "secret_key",
                                        "value": "dowXMENCBpvV6pQ1PtTiMtFRzMmeHu"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "hue-KT_RENEWER-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "KT_RENEWER",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "7bbtiv3vir4220a1erupahn2d"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "Hue"
                },
                {
                    "name": "impala",
                    "type": "IMPALA",
                    "config": {
                        "roleTypeConfigs": [
                            {
                                "roleType": "CATALOGSERVER",
                                "items": [
                                    {
                                        "name": "catalogd_embedded_jvm_heapsize",
                                        "value": "52428800"
                                    }
                                ]
                            },
                            {
                                "roleType": "IMPALAD",
                                "items": [
                                    {
                                        "name": "impalad_memory_limit",
                                        "value": "268435456"
                                    },
                                    {
                                        "name": "scratch_dirs",
                                        "value": "/data/impala/impalad,/mnt/resource/impala/impalad"
                                    }
                                ]
                            }
                        ],
                        "items": [
                            {
                                "name": "hdfs_service",
                                "value": "hdfs"
                            },
                            {
                                "name": "hive_service",
                                "value": "hive"
                            },
                            {
                                "name": "llama_am_ha_zk_auth_secret_key",
                                "value": "WfB51zMphmikKQRLXEq8gQWCm3aBJu"
                            },
                            {
                                "name": "rm_dirty",
                                "value": "true"
                            },
                            {
                                "name": "sentry_service",
                                "value": "sentry"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "impala-CATALOGSERVER-dc8c6a0c641fa6adf7137c6fe69c819e",
                            "type": "CATALOGSERVER",
                            "hostRef": {
                                "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "conk1475zcq7q986aap1heynj"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "impala-IMPALAD-061dbb38888a8734039a66c0e2b4e502",
                            "type": "IMPALAD",
                            "hostRef": {
                                "hostId": "5eac8760-36e1-48dc-b3a4-4669a6b4beec"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "56yaetcnql1vkul9u4mlmros4"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "impala-IMPALAD-63fef2965a4ccd083e20e3d86d4c6cc4",
                            "type": "IMPALAD",
                            "hostRef": {
                                "hostId": "c5b9804d-f59b-402f-9f44-29f091c38879"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "2xaygqqlgxoyw9xaw31qa7zf6"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "impala-IMPALAD-99e8666d2e96d77eeeae2e791b4f5adb",
                            "type": "IMPALAD",
                            "hostRef": {
                                "hostId": "98a7cb3a-ecab-4f7a-946e-4f6695cac73e"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "9i0q8u3b4gen10v8ljj6a06s3"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "impala-IMPALAD-b83abe99e79bed5ed38461d7bcf27333",
                            "type": "IMPALAD",
                            "hostRef": {
                                "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "72m9lglcadvp0l4tswpd8lv8d"
                                    }
                                ]
                            }
                        },
                        {
                            "name": "impala-STATESTORE-dc8c6a0c641fa6adf7137c6fe69c819e",
                            "type": "STATESTORE",
                            "hostRef": {
                                "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "6zncuipff1ozwch2wcgqdijzp"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "Impala"
                },
                {
                    "name": "sentry",
                    "type": "SENTRY",
                    "config": {
                        "roleTypeConfigs": [
                            {
                                "roleType": "SENTRY_SERVER",
                                "items": [
                                    {
                                        "name": "sentry_server_java_heapsize",
                                        "value": "268435456"
                                    }
                                ]
                            }
                        ],
                        "items": [
                            {
                                "name": "hdfs_service",
                                "value": "hdfs"
                            },
                            {
                                "name": "sentry_server_database_host",
                                "value": "node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net"
                            },
                            {
                                "name": "sentry_server_database_password",
                                "value": "sentry"
                            },
                            {
                                "name": "sentry_service_admin_group",
                                "value": "hive,diegozone,impala,hue,solr,kafka,hbase"
                            },
                            {
                                "name": "zookeeper_service",
                                "value": "zookeeper"
                            }
                        ]
                    },
                    "roles": [
                        {
                            "name": "sentry-GATEWAY-99e8666d2e96d77eeeae2e791b4f5adb",
                            "type": "GATEWAY",
                            "hostRef": {
                                "hostId": "98a7cb3a-ecab-4f7a-946e-4f6695cac73e"
                            },
                            "config": {
                                "items": []
                            }
                        },
                        {
                            "name": "sentry-SENTRY_SERVER-dc8c6a0c641fa6adf7137c6fe69c819e",
                            "type": "SENTRY_SERVER",
                            "hostRef": {
                                "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                            },
                            "config": {
                                "items": [
                                    {
                                        "name": "role_jceks_password",
                                        "value": "dy75fibd3piu6076ynf0wluq4"
                                    }
                                ]
                            }
                        }
                    ],
                    "displayName": "Sentry"
                }
            ]
        }
    ],
    "hosts": [
        {
            "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d",
            "ipAddress": "10.0.1.13",
            "hostname": "node01.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net",
            "rackId": "/default",
            "config": {
                "items": []
            }
        },
        {
            "hostId": "98a7cb3a-ecab-4f7a-946e-4f6695cac73e",
            "ipAddress": "10.0.1.14",
            "hostname": "node02.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net",
            "rackId": "/default",
            "config": {
                "items": []
            }
        },
        {
            "hostId": "c5b9804d-f59b-402f-9f44-29f091c38879",
            "ipAddress": "10.0.1.15",
            "hostname": "node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net",
            "rackId": "/default",
            "config": {
                "items": []
            }
        },
        {
            "hostId": "5eac8760-36e1-48dc-b3a4-4669a6b4beec",
            "ipAddress": "10.0.1.16",
            "hostname": "node04.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net",
            "rackId": "/default",
            "config": {
                "items": []
            }
        },
        {
            "hostId": "b021059b-b3c7-4bb2-b64a-6f21aa4c8f2d",
            "ipAddress": "10.0.1.12",
            "hostname": "node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net",
            "rackId": "/default",
            "config": {
                "items": []
            }
        }
    ],
    "users": [
        {
            "name": "__cloudera_internal_user__hue-HUE_SERVER-b83abe99e79bed5ed38461d7bcf27333",
            "roles": [
                "ROLE_NAVIGATOR_ADMIN"
            ],
            "pwHash": "772e2eeffa14c180d071295c8d2ab46c807b62fcd30cc598cd479a135279b520",
            "pwSalt": 2933185723628333497,
            "pwLogin": true
        },
        {
            "name": "__cloudera_internal_user__mgmt-EVENTSERVER-dc8c6a0c641fa6adf7137c6fe69c819e",
            "roles": [
                "ROLE_USER"
            ],
            "pwHash": "7536d32a5b3b919d147809243a48815cd3e33f87019b3cb9ef01b9377da9e5cb",
            "pwSalt": 1173888121201724833,
            "pwLogin": true
        },
        {
            "name": "__cloudera_internal_user__mgmt-HOSTMONITOR-dc8c6a0c641fa6adf7137c6fe69c819e",
            "roles": [
                "ROLE_USER"
            ],
            "pwHash": "7964d2b0af4b7afcdaba6b948bd7ebb1199d0977773be88356a1e2b11520a0c1",
            "pwSalt": 7940567192368332559,
            "pwLogin": true
        },
        {
            "name": "__cloudera_internal_user__mgmt-REPORTSMANAGER-dc8c6a0c641fa6adf7137c6fe69c819e",
            "roles": [
                "ROLE_USER"
            ],
            "pwHash": "9275ab75904221197abfef9c3fb4b7d64c2da456f93f21c97c14fc91028cecbb",
            "pwSalt": 7235030913238762794,
            "pwLogin": true
        },
        {
            "name": "__cloudera_internal_user__mgmt-SERVICEMONITOR-dc8c6a0c641fa6adf7137c6fe69c819e",
            "roles": [
                "ROLE_USER"
            ],
            "pwHash": "16eef532ded3a722ddb5188cb61194bd059b181a11f6a840f1e479468b6b34c4",
            "pwSalt": -1758467861974352757,
            "pwLogin": true
        },
        {
            "name": "admin",
            "roles": [
                "ROLE_LIMITED"
            ],
            "pwHash": "d7fc8fa7281551e6bb45e305c0f374ba3c28c760f744962aec4f32d0d4cbb947",
            "pwSalt": -5194253304404623139,
            "pwLogin": true
        },
        {
            "name": "diegozone",
            "roles": [
                "ROLE_ADMIN"
            ],
            "pwHash": "4a99aaaca6d4bcfb8efef8f452fe3d9adda72b50ddc4207a15bd91f08d1e6711",
            "pwSalt": 6211256293051237077,
            "pwLogin": true
        },
        {
            "name": "minotaur",
            "roles": [
                "ROLE_CONFIGURATOR"
            ],
            "pwHash": "8f458e18027afa433aecee7faf473a897ebf8489c9ff00bbdd8c068716d9a659",
            "pwSalt": 1053009286927740669,
            "pwLogin": true
        }
    ],
    "versionInfo": {
        "version": "5.15.1",
        "buildUser": "jenkins",
        "buildTimestamp": "20180731-0834",
        "gitHash": "6e046fd999fd99e7e12299386ba69b23afa43c60",
        "snapshot": false
    },
    "managementService": {
        "name": "mgmt",
        "type": "MGMT",
        "config": {
            "roleTypeConfigs": [
                {
                    "roleType": "EVENTSERVER",
                    "items": [
                        {
                            "name": "event_server_heapsize",
                            "value": "915406848"
                        }
                    ]
                },
                {
                    "roleType": "HOSTMONITOR",
                    "items": [
                        {
                            "name": "firehose_heapsize",
                            "value": "915406848"
                        },
                        {
                            "name": "firehose_non_java_memory_bytes",
                            "value": "1190133760"
                        }
                    ]
                },
                {
                    "roleType": "REPORTSMANAGER",
                    "items": [
                        {
                            "name": "headlamp_database_host",
                            "value": "node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net"
                        },
                        {
                            "name": "headlamp_database_name",
                            "value": "rman"
                        },
                        {
                            "name": "headlamp_database_password",
                            "value": "rman"
                        },
                        {
                            "name": "headlamp_database_user",
                            "value": "rman"
                        },
                        {
                            "name": "headlamp_heapsize",
                            "value": "915406848"
                        }
                    ]
                },
                {
                    "roleType": "SERVICEMONITOR",
                    "items": [
                        {
                            "name": "firehose_heapsize",
                            "value": "915406848"
                        },
                        {
                            "name": "firehose_non_java_memory_bytes",
                            "value": "1190133760"
                        }
                    ]
                }
            ],
            "items": []
        },
        "roles": [
            {
                "name": "mgmt-ALERTPUBLISHER-dc8c6a0c641fa6adf7137c6fe69c819e",
                "type": "ALERTPUBLISHER",
                "hostRef": {
                    "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                },
                "config": {
                    "items": [
                        {
                            "name": "role_jceks_password",
                            "value": "1388b46t8dlgolze80wfssiqm"
                        }
                    ]
                }
            },
            {
                "name": "mgmt-EVENTSERVER-dc8c6a0c641fa6adf7137c6fe69c819e",
                "type": "EVENTSERVER",
                "hostRef": {
                    "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                },
                "config": {
                    "items": [
                        {
                            "name": "role_jceks_password",
                            "value": "5xzz1ttinel2jw5v3zk0cp460"
                        }
                    ]
                }
            },
            {
                "name": "mgmt-HOSTMONITOR-dc8c6a0c641fa6adf7137c6fe69c819e",
                "type": "HOSTMONITOR",
                "hostRef": {
                    "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                },
                "config": {
                    "items": [
                        {
                            "name": "role_jceks_password",
                            "value": "35uxma4q70ceqld659aaxilv8"
                        }
                    ]
                }
            },
            {
                "name": "mgmt-REPORTSMANAGER-dc8c6a0c641fa6adf7137c6fe69c819e",
                "type": "REPORTSMANAGER",
                "hostRef": {
                    "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                },
                "config": {
                    "items": [
                        {
                            "name": "role_jceks_password",
                            "value": "99ro94vcychp7c1zw70p523nz"
                        }
                    ]
                }
            },
            {
                "name": "mgmt-SERVICEMONITOR-dc8c6a0c641fa6adf7137c6fe69c819e",
                "type": "SERVICEMONITOR",
                "hostRef": {
                    "hostId": "23a0093d-3295-443f-89cb-3ef29101ff8d"
                },
                "config": {
                    "items": [
                        {
                            "name": "role_jceks_password",
                            "value": "85xdvyq3x9hse7de9idyvj1"
                        }
                    ]
                }
            }
        ],
        "displayName": "Cloudera Management Service"
    },
    "managerSettings": {
        "items": [
            {
                "name": "AD_USE_SIMPLE_AUTH",
                "value": "false"
            },
            {
                "name": "CLUSTER_STATS_START",
                "value": "10/24/2012 16:40"
            },
            {
                "name": "KDC_ADMIN_HOST",
                "value": "node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net"
            },
            {
                "name": "KDC_ADMIN_PASSWORD",
                "value": "BQIAAABPAAEADEJPT1RDQU1QLkNPTQAMY2xvdWRlcmEtc2NtAAAAAVxkNzQBABIAIOSKIjI6ZE8PSdRgfOgahdnRsQ6gkE2sKmB5ehWPnDx1AAAAAQ=="
            },
            {
                "name": "KDC_ADMIN_USER",
                "value": "cloudera-scm@BOOTCAMP.COM"
            },
            {
                "name": "KDC_HOST",
                "value": "node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net"
            },
            {
                "name": "KRB_DOMAIN",
                "value": "d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net,.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net"
            },
            {
                "name": "KRB_ENC_TYPES",
                "value": "aes256-cts"
            },
            {
                "name": "KRB_MANAGE_KRB5_CONF",
                "value": "true"
            },
            {
                "name": "PUBLIC_CLOUD_STATUS",
                "value": "NOT_ON_PUBLIC_CLOUD"
            },
            {
                "name": "REMOTE_PARCEL_REPO_URLS",
                "value": "http://node05/cloudera-parcels/cdh5/parcels/5.15.1/,http://node05/cloudera-parcels/accumulo-c5/parcels/1.7.2/,http://node05/cloudera-parcels/kafka/parcels/latest/,http://node05/cloudera-parcels/spark/parcels/2.3.0.cloudera3/,http://node05/cloudera-parcels/sqoop-connectors/parcels/latest/,http://node05/cloudera-parcels/gplextras5/parcels/5.15.1/"
            },
            {
                "name": "SECURITY_REALM",
                "value": "BOOTCAMP.COM"
            }
        ]
    }
}
```
