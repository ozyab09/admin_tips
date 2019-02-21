# Keepalived

## Installing
```
yum install keepalived -y 
```

## Edit config file /etc/keepalived/keepalived.conf

```
! Configuration File for keepalived

global_defs {
   notification_email {
     it@domain.name
   }
   notification_email_from keepalived@domain.name
   smtp_server localhost
   smtp_connect_timeout 30
}


vrrp_instance VI_1 {
  interface enp6s0f0            # your interface 
  state BACKUP                  # MASTER on main server, BACKUP on slave
  virtual_router_id 51          # one id for all servers
  priority 100                  # 101 for main server, 100 for slave
  advert_int 1
  authentication {
        auth_type PASS
        auth_pass your_pass
    }

  virtual_ipaddress {
    192.168.10.XXX               # virtual ip address
  }
}
```

## Start keepalived service
```
systemctl start keepalived
```