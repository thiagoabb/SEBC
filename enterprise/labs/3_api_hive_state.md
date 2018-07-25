# Lab 3 CM API HIVE 
```
<Stop Start Request>
curl -u admin:admin "http://40.78.21.69:7180/api/v2/clusters/thiagoabb/services/hive/commands/stop"
curl -u admin:admin "http://40.78.21.69:7180/api/v2/clusters/thiagoabb/services/hive/commands/start"
```

```
< List Status Request>

curl -u admin:admin "http://40.78.21.69:7180/api/v2/clusters/thiagoabb/services/hive"

<output>
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://cloudera-1.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false,
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive"
```