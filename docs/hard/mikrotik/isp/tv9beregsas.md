# ISP Tv9 Beregsas

## RouterOS v7

```shell
/ipv6/settings/set accept-redirects=no disable-ipv6=no forward=yes
/ipv6/nd/prefix/default/set valid-lifetime=1h preferred-lifetime=30m autonomous=yes
/ipv6/nd/set [ find default=yes ] advertise-dns=yes ra-lifetime=30m
/ipv6/dhcp-client/add add-default-route=yes use-peer-dns=yes request=prefix interface=ether1 pool-name=Tv9Beregsas pool-prefix-length=64
/ipv6/address/add from-pool=Tv9Beregsas advertise=yes interface=ether1
```
