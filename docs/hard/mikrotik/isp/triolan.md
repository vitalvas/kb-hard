# ISP Triolan

```
/ipv6 nd prefix default set valid-lifetime=1h preferred-lifetime=30m autonomous=yes
/ipv6 nd set [ find default=yes ] advertise-dns=no ra-lifetime=30m
/ipv6 dhcp-client add add-default-route=yes interface=ether2 pool-name=Triolan request=prefix use-peer-dns=no
```
