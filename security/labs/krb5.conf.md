# Lab 1 krb5.conf
```
[root@cloudera-1 ~]# cat /etc/krb5.conf
# Configuration snippets may be placed in this directory as well
includedir /etc/krb5.conf.d/

[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 udp_preference_limit = 1
 default_tgs_enctypes = aes256-cts
 default_tkt_enctypes = aes256-cts
 default_realm = CLOUDERA


[realms]
 CLOUDERA = {
  kdc = cloudera-1.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net
  admin_server = cloudera-1.fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net
 }

[domain_realm]
 .fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net = CLOUDERA
 fun0dz1xt0vubf40ygo12pr4uh.dx.internal.cloudapp.net = CLOUDERA
```