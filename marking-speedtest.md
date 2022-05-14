


#### ADD SPEEDTEST ADDRESS LIST

```sh

/ip firewall address-list add list="ip-client" address=192.168.1.0/24

```

#### ADD SPEEDTEST ADDRESS LIST

##### EXAMPLE FILE : [SPEEDTEST ADDRESS LIST](/speedtest-address-list.md)
```sh

/ip firewall address-list add address=yougetsignal.com list=speedtest

```
#### ADD MARK ROUTING
```sh

/ip firewall mangle add action=mark-routing chain=prerouting dst-address-list=speedtest new-routing-mark=SPEEDTEST-MARK passthrough=no src-address-list=ip-client

```

#### ADD ROUTE
```sh

/ip route add check-gateway=ping distance=1 gateway=VPN-INTERFACE routing-mark=SPEEDTEST-MARK

```