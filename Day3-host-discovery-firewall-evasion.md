## Objective
To understand host discovery techniques, firewall filtering behavior,
and how Nmap scan types react under restricted environments.

## Techniques Practiced
- Host discovery (-sn, -Pn)
- XMAS scan (-sX)
- Fast scan (-F)
- Aggressive scan (-A)
- Packet fragmentation (-f)
- Timing templates (-T)
- TTL observation

## Commands Used
'''bash

nmap 157.240.0.xxx -v -F
nmap 157.240.0.xxx -v -Pn
nmap 157.240.0.0/24 -v -sn
nmap 34.120.54.0/24 -vv -sX
nmap 142.250.184.xxx -vv -p- -T4
nmap 34.120.54.0/24 -vv -A

## Observations
- ICMP-based discovery is often blocked by firewalls.
- XMAS scans resulted in open|filtered states due to silent packet drops.
- Using -Pn allowed scanning even when hosts blocked ping requests.
- Fast scans may miss hosts unless host discovery is bypassed.
- Standard web ports (80, 443) are commonly allowed through firewalls.
- TTL values remained consistent, indicating cloud or standardized OS behavior.

## Learning
Firewalls rely heavily on traffic patterns, protocol flags, and packet
structure. By modifying scan techniques and avoiding default discovery
methods, it is possible to infer host availability even when direct
responses are blocked. This highlights why layered defenses (firewall,
IDS, rate-limiting) are critical in real-world networks.
