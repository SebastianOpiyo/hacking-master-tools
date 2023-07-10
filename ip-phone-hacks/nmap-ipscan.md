# SCAN A NETWORK FOR IP PHONES
`nmap -sS -p 10000-20000 -T4 <target IP>`

`-sS` --> option tells nmap to perform a SYN scan, a less intrusive way to scan for open ports.
`-p 10000-20000` tells nmap to scan the ports 10000 to 20000, which are ports commonly used by IP Phones. 
`-T4` tells Nmap to run the scan in more aggressive mode.
`target IP` is the IP address of the network that you want to scan.

## Example
`nmap -sS -p 10000-20000 -T4 192.168.1.0/24`

## Example Output
Starting Nmap 7.91 ( https://nmap.org ) at 2023-07-10 07:38 UTC
Nmap scan report for 192.168.1.0
Host is up (0.036s latency).
Not filtered
PORT     STATE SERVICE
10000/tcp open  Cisco IP Phone
10001/tcp open  Cisco IP Phone
10002/tcp open  Cisco IP Phone


## Scan for Operating System
`nmap -sS -p 10000-20000 -O 192.168.1.0/24`