# Dual WAN (WIP)

```
/ip firewall mangle add action=mark-connection chain=input in-interface=pppoe-out1 new-connection-mark=cin_ISP1
/ip firewall mangle add action=mark-connection chain=input in-interface=ether2 new-connection-mark=cin_ISP2

/ip firewall mangle add action=mark-routing chain=output connection-mark=cin_ISP1 new-routing-mark=rout_ISP1 passthrough=no
/ip firewall mangle add action=mark-routing chain=output connection-mark=cin_ISP2 new-routing-mark=rout_ISP2 passthrough=no

/ip route add distance=1 gateway=pppoe-out1 routing-mark=lan_out_ISP1 check-gateway=ping

/ip firewall mangle add src-address-list=lan_out_ISP1-src action=mark-routing chain=prerouting new-routing-mark=lan_out_ISP1
/ip firewall mangle add dst-address-list=lan_out_ISP1-dst action=mark-routing chain=prerouting new-routing-mark=lan_out_ISP1
```
