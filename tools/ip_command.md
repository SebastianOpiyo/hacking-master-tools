# ip Command

It is an improvement of the __ipconfig__ command
Below is a summary of how to use it:

*NOTE: Take special care while using the commands below, especially while working with the ssh remote session. Otherwise you will lose connectivity to the server.*

- To view the manual page
```$ man ip```

- To list all ip addresses associated with all existing network interfaces
```ip a``` or ```ip addr``` or ```ip address```

- Select between IPv4 & IPv6
```ip -4 a``` or ```ip -6 a```

## List particular interface
* ```ip a show eth0```
* ```ip a list eth0```
* ```ip a show dev eth0```

- Only show running interfaces
```ip link ls up```

## Assign IP Addresses to interface(s)
* ```ip a add {ip_addr/mask} dev {interface}```
* eg. ```ip a add 192.168.1.200/24 dev eth0```

## Add broadcast address
* ip addr add brd {ADDDRESS-HERE} dev {interface}
* ip addr add broadcast {ADDDRESS-HERE} dev {interface}
* ip addr add broadcast 172.20.10.255 dev dummy0

Example, using + or - sign instead of broadcast address
```ip addr add 192.168.1.50/24 brd + dev eth0 label eth0Home```

- Remove/Delete IP Address from interface
>```ip a del {ipv6_addr_OR_ipv4_addr} dev {interface}```
>Example: ```ip a del 192.168.1.200/24 dev eth0```

- Flash all IP addresses in bulk from a network:
Example: ```ip -s -s a f to 192.168.2.0/24```

- Disable all IP Addresses on all Point-to-Point(ppp) interfaces
Example: 
1. ```ip -4 addr flush label "ppp*"```
2. ```ip -4 addr flush label "eth*"```

- Change device MODE to UP or DOWN
>```ip link set dev {DEVICE} {up|down}```
>Example: ```ip link set dev eth1 down```

- Set the length of __txqueuelen__ (length of transmit queue) of device 
>```ip link set txqueuelen {NUMBER} dev {DEVICE}```
>E.g change from 1k to 10k```ip link set txqueuelen 10000 dev eth0```

## Change the MTU(Max Transmission Unit) of a device(for gigabit networks) for better network performance
*  ```ip link set mtu {NUMBER} dev {DEVICE}```
* E.g ```ip link set mtu 9000 dev eth0```
* ```ip a list eth0```

## Display neighbour/arp cache
* ```ip n show```
* ```ip neigh show```

## Add new ARP entry
* ```ip neigh add {IP-HERE} lladdr {MAC/LLADDRESS} dev {DEVICE} nud {STATE}```
* E.g. ```ip neigh add 192.168.1.5 lladdr 00:1a:30:38:a8:00 dev eth0 nud perm```

## Delete ARP entry
* ```ip neigh del {IPAddress} dev {DEVICE}```
* E.g ```ip neigh del 192.168.1.5 dev eth1```

## Change state to reachable in this example
>```ip neigh chg 192.168.1.100 dev eth1 nud reachable```

## Flush ARP entry
*  ```ip -s -s n f {IPAddress}```
*  E.g```ip -s -s n f 192.168.1.5```
*  OR 
*  ```ip -s -s n flush 192.168.1.5```


## ```ip route```: Routing Table Management Commands
## Show Routing Table
* ```ip r ```
* ```ip r list```
* ```ip route list```
* ```ip r list [options] ip route```

- Display route for a particular IP
> ```ip r list 192.168.1.0/24```

## Add New Route
* ```ip route add {NETWORK/MASK} via {GATEWAYIP}```
* ```ip route add {NETWORK/MASK} dev {DEVICE}```
* ```## Add default route using ip ##```
* ```ip route add default {NETWORK/MASK} dev {DEVICE}```
* ```ip route add default {NETWORK/MASK} via {GATEWAYIP}```

- Add a plain route to network 192.168.1.0/24 via gateway 192.168.1.254:
> ```ip route add 192.168.1.0/24 via 192.168.1.254```

- To route all traffic via 192.168.1.254 gateway connected via eth0 network interface:
> ```ip route add 192.168.1.0/24 dev eth0```

- Delete Route
> ```ip route del default```
E.g ```ip route del 192.168.1.0/24 dev eth0```

# How to Change MAC Address on Linux
* ```NIC="eno1" ## <-- My NIC name ##```
* ```ip link show $NIC```
* ```ip link set dev $NIC down```
* ```## set new MAC address ##```
* ```ip link set dev $NIC address XX:YY:ZZ:AA:BB:CC```
* ```ip link set dev $NIC up```

## Make ip command output pretty by colouring
* ```ip -c route```

## Showing all IP Addressses on Linux Box
* ```$ sudo ip -br -c link show```
* ```$ sudo ip -br -c addr show```


