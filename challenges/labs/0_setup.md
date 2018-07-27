# Setup Challange 
```
<Provider>

Azure 
```

```
<IP and DNS>
40.78.19.47       cloudera1.westus.cloudapp.azure.com
104.42.254.240    cloudera2.westus.cloudapp.azure.com
40.83.136.191     cloudera3.westus.cloudapp.azure.com
40.83.140.0       cloudera4.westus.cloudapp.azure.com
104.42.150.213    cloudera5.westus.cloudapp.azure.com
```

```
< Version Linux >
Linux Version Centos 7.2
[cloudera@cloudera-1 ~]$ uname -a
Linux cloudera-1 3.10.0-327.28.2.el7.x86_64 #1 SMP Wed Aug 3 11:11:39 UTC 2016 x86_64 x86_64 x86_64 GNU/Linux

```

```
< Data Capacity >
[cloudera@cloudera-1 resource]$ df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda2        50G  1.3G   49G   3% /
devtmpfs         16G     0   16G   0% /dev
tmpfs            16G     0   16G   0% /dev/shm
tmpfs            16G  8.4M   16G   1% /run
tmpfs            16G     0   16G   0% /sys/fs/cgroup
/dev/sda1       240M  124M  100M  56% /boot
/dev/sdb1       668G  2.1G  632G   1% /mnt/resource
tmpfs           3.2G     0  3.2G   0% /run/user/1000
```


```
< Repolist enabled >
[cloudera@cloudera-1 resource]$ yum repolist enabled
Loaded plugins: fastestmirror
base                                                                                                                    | 3.6 kB  00:00:00
extras                                                                                                                  | 3.4 kB  00:00:00
openlogic                                                                                                               | 2.9 kB  00:00:00
updates                                                                                                                 | 3.4 kB  00:00:00
(1/5): extras/7/x86_64/primary_db                                                                                       | 172 kB  00:00:00
(2/5): openlogic/x86_64/primary_db                                                                                      |  72 kB  00:00:00
(3/5): base/x86_64/group_gz                                                                                             | 166 kB  00:00:00
(4/5): base/x86_64/primary_db                                                                                           | 5.9 MB  00:00:00
(5/5): updates/x86_64/primary_db                                                                                        | 4.3 MB  00:00:00
Determining fastest mirrors
repo id                                                 repo name                                                                        status
base/x86_64                                             CentOS-7 - Base                                                                  9,911
extras/7/x86_64                                         CentOS-7 - Extras                                                                  363
openlogic/x86_64                                        CentOS-7 - openlogic packages for x86_64                                           109
updates/x86_64                                          CentOS-7 - Updates                                                               1,004
repolist: 11,387
```