#Challenge 2: Install Cloudera Manager 5.12.X
```
<list yum.repo.d >
[root@cloudera-2 yum.repos.d]# ls /etc/yum.repos.d
CentOS-Base.repo  CentOS-Debuginfo.repo  CentOS-Media.repo    CentOS-Vault.repo      mariadb.repo
CentOS-CR.repo    CentOS-fasttrack.repo  CentOS-Sources.repo  cloudera-manager.repo

```

```
<SCM Prepare outputs>
sh /usr/share/cmf/schema/scm_prepare_database.sh mysql scm scm scm -h 10.0.1.4
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!


```