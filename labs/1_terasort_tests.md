[libdefaults]
default_realm = INFRA.CLARO
dns_lookup_kdc = false
dns_lookup_realm = false
ticket_lifetime = 86400
renew_lifetime = 604800
forwardable = true
default_tgs_enctypes = aes256-cts-hmac-sha1-96
default_tkt_enctypes = aes256-cts-hmac-sha1-96
permitted_enctypes = aes256-cts-hmac-sha1-96
udp_preference_limit = 1
kdc_timeout = 6000
[realms]
INFRA.CLARO = {
kdc = headnode03.hadoop.backbone.claro.com.br
admin_server = headnode03.hadoop.backbone.claro.com.br
}
CORP.CLAROBR = {
kdc = CAADSCP02.corp.clarobr
admin_server = CAADSCP02.corp.clarobr
}
[domain_realm]
hadoop.backbone.claro.com.br = INFRA.CLARO
corp.clarobr = CORP.CLAROBR
[capaths]
INFRA.CLARO = {
CORP.CLAROBR = .
}


#adicionar a relação de confiança entre KDCS
kadmin 
addprinc krbtgt/INFRA.CLARO@CORP.CLAROBR
addprinc krbtgt/CORP.CLAROBR@INFRA.CLARO

kadmin: addprinc -e "aes256-cts:normal aes128-cts:normal rc4-hmac:normal" krbtgt/LABBD.COM.BR@CORP.CLAROBR
kadmin: addprinc -e "aes256-cts:normal aes128-cts:normal rc4-hmac:normal" krbtgt/CORP.CLAROBR@LABBD.COM.BR

#Adicionar no CM de Engenharia
# HDFS - Configuration - Trusted Kerberos Realms
Cluster A - Adicionar Healm  (CORP.CLAROBR)

#Criar um usuário que tenha as mesmas credencias nos 2 Realms, usr e passwd tem que ser iguais
KDC INFRA.CLARO
kadmin
addprinc -pw user user@INFRA.CLARO

KDC CORP.CLAROBR
kadmin
addprinc -pw user user@CORP.CLAROBR

Após isso será necessário realizar testes de acesso ao cluster de Engenharia usando uma keytab/acesso do ambiente de TI.


