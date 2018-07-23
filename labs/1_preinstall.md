# Lab 1 pre-install configs md
```
<swappines config>
<sysctl vm.swappiness=1>
<echo "vm.swappiness = 1" >> /etc/sysctl.conf>

<output - sysctl vm.swappiness>
![Cat](https://github.com/thiagoabb/SEBC/blob/master/labs/png/swappiness.PNG)
```

```
<hugepages config>
<echo 'never' > /sys/kernel/mm/transparent_hugepage/defrag>
<echo 'echo "never > /sys/kernel/mm/transparent_hugepage/defrag"' >> /etc/rc.local>
<echo 'echo "never > /sys/kernel/mm/transparent_hugepage/enabled"' >> /etc/rc.local>

<output - cat  /sys/kernel/mm/transparent_hugepage/defrag>
<output2 - cat /etc/rc.local>
![alt text](http://url/to/img.png)
```

```
<Mount option/list>
<output - cat /etc/fstab>
<output2 - df -h >
![alt text](http://url/to/img.png)
```

```
< Free space >
<output - dumpe2fs /dev/sda2 | grep -i reserved>
<>
<>
![alt text](http://url/to/img.png)
```

```
<Network config>
<output - ifconfig -a >
<>
<>
![alt text](http://url/to/img.png)
```

```
<host lookup>
<vi /etc/hosts >
<10.0.0.4 cloudera1.1cwprorqlexetp54iep0t35lse.bx.internal.cloudapp.net cloudera1
10.0.0.5 cloudera2.1cwprorqlexetp54iep0t35lse.bx.internal.cloudapp.net cloudera2
10.0.0.6 cloudera3.1cwprorqlexetp54iep0t35lse.bx.internal.cloudapp.net cloudera3
10.0.0.7 cloudera4.1cwprorqlexetp54iep0t35lse.bx.internal.cloudapp.net cloudera4
10.0.0.8 cloudera5.1cwprorqlexetp54iep0t35lse.bx.internal.cloudapp.net cloudera5>

<output - getent hosts cloudera2 | getent hosts cloudera1 >
![alt text](http://url/to/img.png)
```

```
<nscd service>
<yum install nscd>
<systemctl enable nscd>

<output - systemctl status nscd >
<>
<>
![alt text](http://url/to/img.png)
```

```
<ntp service>
<yum install ntp>
<systemctl enable ntpd>

<output - systemctl status ntpd  >
![alt text](http://url/to/img.png)
```