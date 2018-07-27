#Challenge 3: CHD 5.9X
```
<user home directory>
hadoop fs -mkdir /user/goldengate 
hadoop fs -mkdir /user/caldecott
hadoop fs -chown goldengate:bridge /user/goldengate
hadoop fs -chown caldecott:tunnel /user/caldecott
```

```
<hdfs ls>
hdfs dfs -ls /user
[hdfs@cloudera-2 root]$ hadoop fs -ls /user
Found 6 items
drwxr-xr-x   - caldecott  tunnel          0 2018-07-27 17:47 /user/caldecott
drwxr-xr-x   - goldengate bridge          0 2018-07-27 17:47 /user/goldengate
drwxrwxrwx   - mapred     hadoop          0 2018-07-27 17:46 /user/history
drwxrwxr-t   - hive       hive            0 2018-07-27 17:46 /user/hive
drwxrwxr-x   - hue        hue             0 2018-07-27 17:47 /user/hue
drwxrwxr-x   - oozie      oozie           0 2018-07-27 17:47 /user/oozie


```

```
<API CALL service>
curl -u admin:admin "http://localhost:7180/api/v14/clusters/thiagoabb/services"

[hdfs@cloudera-2 root]$ curl -u admin:admin "http://localhost:7180/api/v14/clusters/thiagoabb/services"
{
  "message" : "Cluster 'thiagoabb' not found."
}[hdfs@cloudera-2 root]$ curl -u admin:admin "http://localhost:7180/api/v14/clusters/thiagoabb/services"
{
  "items" : [ {
    "name" : "hive",
    "type" : "HIVE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/hive",
    "roleInstancesUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/hive/instances",
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
  }, {
    "name" : "hbase",
    "type" : "HBASE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/hbase",
    "roleInstancesUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/hbase/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HBASE_MASTER_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HBASE_REGION_SERVERS_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HBase",
    "entityStatus" : "GOOD_HEALTH"
  }, {
    "name" : "zookeeper",
    "type" : "ZOOKEEPER",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/zookeeper",
    "roleInstancesUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/zookeeper/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "ZOOKEEPER_CANARY_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "ZOOKEEPER_SERVERS_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "ZooKeeper",
    "entityStatus" : "GOOD_HEALTH"
  }, {
    "name" : "hue",
    "type" : "HUE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/hue",
    "roleInstancesUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/hue/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HUE_HUE_SERVERS_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HUE_LOAD_BALANCER_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Hue",
    "entityStatus" : "GOOD_HEALTH"
  }, {
    "name" : "oozie",
    "type" : "OOZIE",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/oozie",
    "roleInstancesUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/oozie/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "OOZIE_OOZIE_SERVERS_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "Oozie",
    "entityStatus" : "GOOD_HEALTH"
  }, {
    "name" : "yarn",
    "type" : "YARN",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/yarn",
    "roleInstancesUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/yarn/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "YARN_JOBHISTORY_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "YARN_NODE_MANAGERS_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "YARN_RESOURCEMANAGERS_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "YARN_USAGE_AGGREGATION_HEALTH",
      "summary" : "DISABLED",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "YARN (MR2 Included)",
    "entityStatus" : "GOOD_HEALTH"
  }, {
    "name" : "hdfs",
    "type" : "HDFS",
    "clusterRef" : {
      "clusterName" : "cluster"
    },
    "serviceUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/hdfs",
    "roleInstancesUrl" : "http://cloudera-2.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/hdfs/instances",
    "serviceState" : "STARTED",
    "healthSummary" : "GOOD",
    "healthChecks" : [ {
      "name" : "HDFS_BLOCKS_WITH_CORRUPT_REPLICAS",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_CANARY_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_DATA_NODES_HEALTHY",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_FREE_SPACE_REMAINING",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_HA_NAMENODE_HEALTH",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_MISSING_BLOCKS",
      "summary" : "GOOD",
      "suppressed" : false
    }, {
      "name" : "HDFS_UNDER_REPLICATED_BLOCKS",
      "summary" : "GOOD",
      "suppressed" : false
    } ],
    "configStalenessStatus" : "FRESH",
    "clientConfigStalenessStatus" : "FRESH",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "displayName" : "HDFS",
    "entityStatus" : "GOOD_HEALTH"
  } ]
}

```

```
<API CALL hosts>
curl -u admin:admin "http://localhost:7180/api/v14/clusters/thiagoabb/hosts"

[hdfs@cloudera-2 root]$ curl -u admin:admin "http://localhost:7180/api/v14/clusters/thiagoabb/hosts"
{
  "items" : [ {
    "hostId" : "cecc3729-4835-49cd-817a-5789a5d425de"
  }, {
    "hostId" : "5b5d986a-56e6-40e2-9a95-4f9f99356060"
  }, {
    "hostId" : "d252cd25-f51d-4d28-8a71-8712acdb7061"
  }, {
    "hostId" : "dcf0d5ac-3652-4ad2-b684-2ff14ac4e8a8"
  }, {
    "hostId" : "17fe575e-c5e8-4ccd-b032-149fc71e7d45"
  } ]
}

```