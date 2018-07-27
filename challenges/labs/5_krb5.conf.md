#Challenge 5: KRB5.CONF FILE
```
[libdefaults]
default_realm = THIAGOABB.SFO
dns_lookup_kdc = false
dns_lookup_realm = false
ticket_lifetime = 86400
renew_lifetime = 604800
forwardable = true
default_tgs_enctypes = aes256-cts
default_tkt_enctypes = aes256-cts
permitted_enctypes = aes256-cts
udp_preference_limit = 1
kdc_timeout = 3000
[realms]
THIAGOABB.SFO = {
kdc = cloudera-5.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net
admin_server = cloudera-5.nnfosyzsuxke1kd0uv1k4sqibc.dx.internal.cloudapp.net
}
[domain_realm]

```