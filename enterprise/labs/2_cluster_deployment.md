# Lab 2 CM API
```
< Curl Request >
curl -u admin:admin "http://localhost:7180/api/v2/cm/deployment"
```
```
<RESULT>
{
  "timestamp" : "2018-07-25T19:28:56.116Z",
  "clusters" : [ {
    "name" : "thiagoabb",
    "version" : "CDH5",
    "services" : [ {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "2353004544"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "235300454"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "2353004544"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "3865470566"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "15720565964"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "409"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "2645"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "cloudera-1.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-6910d848956a887a135402e925ae0868",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "78d4af17-2b04-4dd7-af33-bf4ceca5c69e"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-af887e87bde8d13c086bc3e52f66baa7",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "29sz2ylaz5bip6x9pw0ww89ni"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-af887e87bde8d13c086bc3e52f66baa7",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bmh2ke3m9jpkpb221lomtv8he"
          } ]
        }
      } ],
      "displayName" : "Hive"
    }, {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-47f733f5a779919857491c170f5345fb",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "105e46fb-f9f3-4e9b-9c70-bbb67ad8ce12"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3n1xyp3huv3ppse9nvy32ug1b"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-af887e87bde8d13c086bc3e52f66baa7",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "61jyisxlg698f6gnkoe6oyf1i"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-afd5c664b326e2c7ccaad27e553b8ae1",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "cac7338b-742d-4d2a-8b6c-723749fd6082"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ehwfslne9l20r727o70mp3sgj"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "cloudera-1.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net"
        }, {
          "name" : "database_password",
          "value" : "hue"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-af887e87bde8d13c086bc3e52f66baa7"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-6910d848956a887a135402e925ae0868",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "78d4af17-2b04-4dd7-af33-bf4ceca5c69e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5813cyb4ag3liehpbgbh7ln5g"
          }, {
            "name" : "secret_key",
            "value" : "AfzaSEC3HKvniX6OFymgFvlgivCPsZ"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "cloudera-1.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-6910d848956a887a135402e925ae0868",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "78d4af17-2b04-4dd7-af33-bf4ceca5c69e"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2ffpy330cx8lzj8ydvibtmrgv"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/mnt/resource/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/mnt/resource/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "4"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "17638"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "18969"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "4"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "sMpVEDGgpjHsdwjxy45JjcAlx86ghA"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-af887e87bde8d13c086bc3e52f66baa7",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3hlulhhsdijaybxnml4avt8ei"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-47f733f5a779919857491c170f5345fb",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "105e46fb-f9f3-4e9b-9c70-bbb67ad8ce12"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "60wybp8sebayyhubdumv7mn0u"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-afd5c664b326e2c7ccaad27e553b8ae1",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "cac7338b-742d-4d2a-8b6c-723749fd6082"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3ka1rqesl6wxsntkvjikvg5a5"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-dd55cde2e98587075992741ecbaa3152",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "f9288123-0f43-489c-920d-bfe23dccbce1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6c2cn4cd62jki2p5ip5gce24z"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-af887e87bde8d13c086bc3e52f66baa7",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "43"
          }, {
            "name" : "role_jceks_password",
            "value" : "a9g9a4qj3lr2ihg88z8rethps"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "dfs_data_dir_list",
            "value" : "/mnt/resource/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "6750572953"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/mnt/resource/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/mnt/resource/dfs/snn"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "oaNVuBhf8JLk4zbfjOWEBgiRh7dSZi"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "C7ZGlGzVOf0BM3ssEGiV4eOIYDotXm"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "8ZwaLa5w3GSq6JQriH6q7APhJ5xneu"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-af887e87bde8d13c086bc3e52f66baa7",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-47f733f5a779919857491c170f5345fb",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "105e46fb-f9f3-4e9b-9c70-bbb67ad8ce12"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9n4utir34y8u1rqd6kenywszy"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-afd5c664b326e2c7ccaad27e553b8ae1",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "cac7338b-742d-4d2a-8b6c-723749fd6082"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a1j0l6ooijru0bz6dudpamthk"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-dd55cde2e98587075992741ecbaa3152",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "f9288123-0f43-489c-920d-bfe23dccbce1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "550uykcy3rz3u9f5urh9wl1bi"
          } ]
        }
      }, {
        "name" : "hdfs-GATEWAY-6910d848956a887a135402e925ae0868",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "78d4af17-2b04-4dd7-af33-bf4ceca5c69e"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-NAMENODE-af887e87bde8d13c086bc3e52f66baa7",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
        },
        "config" : {
          "items" : [ {
            "name" : "namenode_id",
            "value" : "46"
          }, {
            "name" : "role_jceks_password",
            "value" : "bsoru71qm6m9pum2lhh27uhnv"
          } ]
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-af887e87bde8d13c086bc3e52f66baa7",
        "type" : "SECONDARYNAMENODE",
        "hostRef" : {
          "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bt1sirj0186jzfatfe8dohio5"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "78d4af17-2b04-4dd7-af33-bf4ceca5c69e",
    "ipAddress" : "10.0.0.4",
    "hostname" : "cloudera-1.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256",
    "ipAddress" : "10.0.0.5",
    "hostname" : "cloudera-2.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "105e46fb-f9f3-4e9b-9c70-bbb67ad8ce12",
    "ipAddress" : "10.0.0.6",
    "hostname" : "cloudera-3.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "cac7338b-742d-4d2a-8b6c-723749fd6082",
    "ipAddress" : "10.0.0.7",
    "hostname" : "cloudera-4.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "f9288123-0f43-489c-920d-bfe23dccbce1",
    "ipAddress" : "10.0.0.8",
    "hostname" : "cloudera-5.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-af887e87bde8d13c086bc3e52f66baa7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "10aa473aada04cfa344fa8b8e701f318676f824793b995d37bddc21069f8dd64",
    "pwSalt" : 6591547123437493374,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-af887e87bde8d13c086bc3e52f66baa7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "14c2e3e961796edf7533706bac3a262f6e560683e6ffe6b6dc8cd99fe323689f",
    "pwSalt" : 2541032688207513505,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-af887e87bde8d13c086bc3e52f66baa7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "4019af395808962915af86eefc59ddd0b4320a9bc7b4f1780e5c4a0bb556e8a6",
    "pwSalt" : 5161902312810194226,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-af887e87bde8d13c086bc3e52f66baa7",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "9ca0a9830b29646c34e30411b7239a90edfa656c708fa6c6e54fb47d6d666589",
    "pwSalt" : 9044077873809754848,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "4773f9455ed91e114f915f283d638f9ab025450a72399928416f64bfb0b1de99",
    "pwSalt" : 6327057052850771333,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "83cc4a6a36d56021d5436a98eaeb339ada62969e2b5e01d7ec4bd3a331bc0906",
    "pwSalt" : -919828141114302595,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.9.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170627-1506",
    "gitHash" : "23506bb4e114dd460bdac64c57a672e6be631907",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "cloudera-1.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-af887e87bde8d13c086bc3e52f66baa7",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6o32egfi2yxtcqm7hnz8h56j7"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-af887e87bde8d13c086bc3e52f66baa7",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ewz5bp2cjbsvuuib1dbpxp8hy"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-af887e87bde8d13c086bc3e52f66baa7",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3g2e6tzwnnqtn2ofzl4mmk1bh"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-af887e87bde8d13c086bc3e52f66baa7",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "4fzocv0g5c8oukak16y4s0hbr"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-af887e87bde8d13c086bc3e52f66baa7",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "99bd3c83-2f70-4677-883e-22f1f3684256"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "dvhxj6ebew8bcy07qm6jli5dh"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/26/2012 23:00"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "NOT_ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
```