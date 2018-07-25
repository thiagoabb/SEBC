# Lab 4 CM API UPGRADE CALLS 
```
curl -u admin:admin "http://40.78.21.69:7180/api/version"

<output>
[root@cloudera-1 cloudera-scm-server]# curl -u admin:admin "http://40.78.21.69:7180/api/version"
v14
```

```
curl -u admin:admin "http://40.78.21.69:7180/api/v14/cm/version"

<output>
[root@cloudera-1 cloudera-scm-server]# curl -u admin:admin "http://40.78.21.69:7180/api/v14/cm/version"
{
  "version" : "5.9.3",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170627-1506",
  "gitHash" : "23506bb4e114dd460bdac64c57a672e6be631907",
  "snapshot" : false
}
```
```
curl -u admin:admin "http://40.78.21.69:7180/api/v14/users"

<output>
[root@cloudera-1 cloudera-scm-server]# curl -u admin:admin "http://40.78.21.69:7180/api/v14/users"
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]

``` 
```
curl -u admin:admin "http://40.78.21.69:7180/api/v14/cm/scmDbInfo" 
 
<output >
 [root@cloudera-1 cloudera-scm-server]#  curl -u admin:admin "http://40.78.21.69:7180/api/v14/cm/scmDbInfo"
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```