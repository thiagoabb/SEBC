<!-- CSS work goes here for the time being -->
<!-- set a:link text-decoration to none -->
<!-- set a:hover text-decoration to underline -->
<!-- http://forums.markdownpad.com/discussion/143/include-pdf-pagebreak-instructions-in-markdown/p1 -->

---
<div style="page-break-after: always;"></div>

# <center> Challenges - July 27, 2018 - FCE New Hire & Cloudera SEBC

* Overview
  * Build a CM-managed CDH cluster and secure it
* Place your work in the `challenges/labs` folder
  * All text files require  Markdown (`.md`) extension and formatting
  * All screenshots must be in PNG format
  * You will create each required file yourself
* You may consult with each other and research online
  * Submit only your own work
* Push to GitHub often -- don't wait until the end
* If you break your cluster, or your cluster breaks you:
  * Push the work you have into GitHub
  * Create an Issue to describe what you think went wrong
  * Notify the instructor

---
<div style="page-break-after: always;"></div>

## <center> Challenge Setup

* Create the Issue `Challenges Setup`
* New Hires: Make sure `mfernest`  and `andreiamaia` are Collaborators
* Partners: Make sure `mfernest` is a Collaborator
* Make sure the default GitHub labels have been properly changed
* Assign the Issue to yourself and label it `started`
* In the file `challenges/labs/0_setup.md`:
  * List the cloud provider you are using (AWS, GCE, Azure, CloudCat, other)
  * List your instances by IP address and DNS name (don't use `/etc/hosts` for this)
  * List the Linux release you are using (either RHEL/CentOS 6.8 or 7.2)
  * List the file system capacity for the first node 
  * List the command and output for `yum repolist enabled` 
* Add the following Linux accounts to all nodes
  * User `goldengate` with a UID of `2150`
  * User `caldecott` with a UID of `2250`
  * Create the group `tunnel` and add `caldecott` to it
  * Create the group `bridge` and add `goldengate` to it
* List the `/etc/passwd` entries for `goldengate` and `caldecott` 
  * Do not list the entire file
* List the `/etc/group` entries for `tunnel` and `bridge` 
  * Do not list the entire file
* Push these updates to GitHub 
* Label your Issue `review` 
* Assign the Issue to an instructor

---
<div style="page-break-after: always;"></div>

## <center> Challenge 1: Install a MySQL server

* Create the Issue `Install MySQL` if you are using RHEL/Centos 6.x
  * Name the Issue `Install MariaDB` if you are using RHEL/CentOS 7.x
* Assign the Issue to yourself and label it `started`
* Install MySQL 5.5 or MariaDB 5.5 server on the first node listed in `0_setup.md`
  * Use a YUM repository to install the package
  * Copy the repo configuration you used to `challenges/labs/1_my-database-server.repo.md`
* On all cluster nodes
  * Install the database client package and JDBC connector jar on all nodes
* Start the database service and create these databases
  * `scm`
  * `rman`
  * `hive`
  * `oozie`
  * `hue`
* Record the following in `challenges/labs/1_db-server.md`
  * The db server command and output that report the server host
  * The db server command and output that report the server version
  * The db server command and output that list the databases 
* Push this work to GitHub
* Label the Issue `review` and assign it to an instructor

---
<div style="page-break-after: always;"></div>

## <center> Challenge 2: Install Cloudera Manager 5.12.x (latest micro release)

* Create the Issue `Install CM`
* Assign yourself and label it `started`
* Install Cloudera Manager on the second node listed in `0_setup.md`
* List the command and output for `ls /etc/yum.repos.d` in `challenges/labs/2_cm.md`
  * Copy `cloudera-manager.repo` to `challenges/labs/2_cloudera-manager.repo.md`
* Connect Cloudera Manager Server to its database
  * Use the `scm_prepare_database.sh` script to create the `db.properties` file 
    * List the full command and its output in `2_cm.md`
* Start the Cloudera Manager server
* In `challenges/labs/2_db.properties.md` add:
  * The first line of the server log
  * The line(s) that contain the phrase "Started Jetty server"
  * The content of the `db.properties` file 
* Push these changes to GitHub and label the Issue `review`
* Assign the issue to an instructor

---
<div style="page-break-after: always;"></div>

## <center> Challenge 3 - Install CDH 5.9.x (latest micro release)

* Create the Issue `Install CDH`
* Assign yourself and label it `started`
* Deploy Coreset services + HBase only
  * Rename your cluster after your GitHub handle
* Create user directories in HDFS for `goldengate` and `caldecott`
* Add the following to `3_cm.md`:
    * The command and output for `hdfs dfs -ls /user`
    * The command and output from the CM API call `../api/v14/hosts` 
    * The command and output from the CM API call `../api/v8/clusters/<githubName>/services`
* Login to Hue and install the Hive sample data 
    * Use `beeline` to display tables in the `default` database 
    * Copy the output to `challenges/labs/3_beeline.md`

* Push this work to GitHub and label the Issue `review`
* Assign the issue to an instructor

---
<div style="page-break-after: always;"></div>

## <center> Challenge 4 - HDFS Testing

* Create the Issue `Test HDFS`
* Assign yourself and label it `started`
* As user `goldengate`, use `teragen` to generate a 65,536,000-record dataset
  * Write the output to 8 files 
  * Set the block size to 64 MB
  * Set the mapper container size to 768 MB
  * Name the target directory `tgen`
  * Use the `time` command to capture job duration
* Put the following in `challenges/labs/4_teragen.md`
  * The full `teragen` command and output 
  * The result of the `time` command
  * The command and output of `hdfs dfs -ls /user/goldengate/tgen`
  * The command and output of `hadoop fsck -blocks /user/goldengate`
* Push this work to GitHub and label the Issue `review`
* Assign the issue to an instructor

---
<div style="page-break-after: always;"></div>

## <center> Challenge 5 - Kerberize the cluster

* Create the Issue `Kerberize cluster`
* Assign the issue to yourself and label it `started`
* Install an MIT KDC on the last node in your cluster
  * Name your realm after your GitHub account name
  * Use `SFO` as a suffix
  * For example: `MFERNEST.SFO`
* Create Kerberos user principals for `goldengate`, `caldecott`, and `cloudera-scm`
  * Assign `cloudera-scm` the privileges needed to create service principals and keytab files
* Kerberize the cluster
* Run the `terasort` program as user `goldengate` with the output target `/user/goldengate/tsort`
  * Copy the command and full output to `challenges/labs/5_terasort.md`
* Run the Hadoop `pi` program as user `caldecott`
  * Use the task parameters to `50` and `100` 
  * Copy the command and full output to `challenges/labs/5_pi.md`
*  Copy the configuration files in `/var/kerberos/krb5kdc/` to your repo:
    * Add the prefix `5_` and the suffix `.md` to the original file name
    * Example: `5_kdc.conf.md`
* Push this work to GitHub and label the Issue `review`
* Assign the issue to the instructor

---
<div style="page-break-after: always;"></div>

## <center> Challenge 6 - Install & Configure the Sentry Service

* Create the Issue `Install Sentry`
  * Label it `started`
* Use Cloudera Manager to install and enable Sentry
* Configure both Hive and Impala to enable Sentry
* Create a role for `webclicks` that can read the `web_logs` database
  * Assign the `bridge` group to this role
* Create a role for `analysis` that can read the `customers` databases
  * Assign the `tunnel` group to this role
* Use `beeline` to select ten records from `web_logs`
* Use `beeswax` to select ten records from `customers`
* Capture each outcome as a screenshot, `6_beeline.png` and `6_beeswax.png`
* Label the issue `review`
* Assign the issue to the instructor
* Push all work to GitHub

---
<div style="page-break-after: always;"></div>

## <center> When time runs out:

* Commit any outstanding changes from your repo to GitHub
* Email to `mfe@cloudera.com` that you have stopped pushing to your repo
* Please fill out [this survey form](https://goo.gl/forms/pmHeHx03zRu3cnlc2)
  * Add your comments to `labs/7_feedback_final.md` -- remember to commit them!

---
<div style="page-break-after: always;"></div>
