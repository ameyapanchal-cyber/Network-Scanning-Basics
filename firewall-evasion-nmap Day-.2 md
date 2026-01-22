## Objective
To understand how firewalls detect scanning activity and how different
Nmap techniques can be used to evade or bypass firewall rules.

## Techniques Tested
- Packet fragmentation (-f)
- MTU manipulation (--mtu)
- Decoy scanning (-D)
- TCP connect scan (-sT)
- Idle/Zombie scan (-sI)

## Commands Used

### Packet Fragmentation
```bash
nmap -sS -f 192.168.154.130
nmap -sS --mtu 192.168.154.130 --source-port 80
nmap -sS 192.168.154.130 --data-length 24
nmap 192.168.154.130  -v -D RND:8
nmap -v -p 80 --script=ipidseq* -iR 100 --open
nmap -sI 34.197.28.130 192.168.154.130 -v -Pn

## Explanation of Flags
-Packet fragmentation (-f):
  splits the packet into small fregments so that the firewall can't detect
-MTU manipulation (--mtu):
  manipulate data in order of 8 multiple
-Source port manipulation (--source-port):
  attempts to bypass firewall rules that trust common service ports.
-Data length modification (--data-length):
  add extra data bytes to alter ther  signature
-Decoy scanning (-D):
  hides the real source IP among multiple decoy addresses
-Idle/Zombie scan (-sI):
  leverage the third party host to scan the targate without revealing attacker's IP

## Learning
I learned how firewalls rely on packet structure, source information,
and traffic patterns to detect scanning activity. By modifying packet
behavior or using indirect scanning techniques, detection can sometimes
be reduced without violating firewall rules. This demonstrated why
modern firewalls and intrusion detection systems (IDS) are essential
for effective network security.

“I learned that firewalls rely heavily on packet patterns and metadata, and small changes in packet structure can affect detection. This is why layered defenses like IDS and behavioral analysis are important.”
