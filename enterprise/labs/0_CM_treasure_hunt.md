# Lab 1 CM Questions
```
<Q>
What is ubertask optimization?

<A>
ubertask optimization
Small jobs that runs sequentially within a single JVM.
"Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings
```
```
<Q>
Where in CM is the Kerberos Security Realm value displayed?
<A>
ADMINITRATION -> SECURITY -> CONFIGURATION -> security_realm
```
```
<Q>
Which CDH service(s) host a property for enabling Kerberos authentication?
<A>
HDFS , YARN
```
```
<Q>
How do you upgrade the CM agents?
<A>
Is possibel to upgrade by de CM interface (Cloudera Manager installs Agent software)
or 
stooping all the cm agents, changing de repo (cm version)
 sudo yum clean all
 sudo yum upgrade cloudera-manager-server cloudera-manager-daemons cloudera-manager-server-db-2 cloudera-manager-agent
```
```
<Q>
Give the tsquery statement used to chart Hue's CPU utilization?
<A>
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=$SERVICENAME
SERVICENAME=HUE
CLUSTERID=1
```
```
<Q>
Name all the roles that make up the Hive service
<A>
gateway
Hive Metastore server
HiveServer2
WebHcat Server
```
```
<Q>
What steps must be completed before integrating Cloudera Manager with Kerberos?
<A>

 Setup KDC (Local or AD)
 KDC condigured with non-zero lifetime ( + renewable propertie )
 If using AD, openladp libs must be installed 
 Admin Account for Cloudera manager, to manage de service credentials
 Download Unlimited JCE policy (Aes 256 )
```
<center> <img src="../labs/png/kerberos.PNG"/> </center>