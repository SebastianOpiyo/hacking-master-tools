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

- List particular interface
```ip a show eth0```
```ip a list eth0```
```ip a show dev eth0```

- Only show running interfaces
```ip link ls up```

- Assign IP Addresses to interface(s)
```ip a add {ip_addr/mask} dev {interface}```
eg. ```ip a add 192.168.1.200/24 dev eth0```

- Add broadcast address
>```ip addr add brd {ADDDRESS-HERE} dev {interface}
>ip addr add broadcast {ADDDRESS-HERE} dev {interface}
>ip addr add broadcast 172.20.10.255 dev dummy0```

Example, using + or - sign instead of broadcast address
```ip addr add 192.168.1.50/24 brd + dev eth0 label eth0Home```

- Remove/Delete IP Address from interface
```ip a del {ipv6_addr_OR_ipv4_addr} dev {interface}```
Example: ```ip a del 192.168.1.200/24 dev eth0```

- Flash all IP addresses in bulk from a network:
Example: ```ip -s -s a f to 192.168.2.0/24```

- Disable all IP Addresses on all Point-to-Point(ppp) interfaces
Example: 
1. ```ip -4 addr flush label "ppp*"```
2. ```ip -4 addr flush label "eth*"```

- Change device MODE to UP or DOWN
```ip link set dev {DEVICE} {up|down}```
Example: ```ip link set dev eth1 down```

- Set the length of __txqueuelen__ (length of transmit queue) of device 
```ip link set txqueuelen {NUMBER} dev {DEVICE}```
E.g ```ip link set txqueuelen 10000 dev eth0```