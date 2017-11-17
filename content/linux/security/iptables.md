---
title: "IPTables"
draft: false
---

{{% panel="Understanding IPTables" header=" Understanding IPTables" theme="default" %}}

# Finish at 19:33

- Different Tables    
    - NAT - Network Address Translation
    - MANGLE - Modifying Packets
    - Filter - Decide which packets get processed


- Tables have chains
    - A chain is a sequential list of rules
    - A Rule defines particular kinds of packets and where they go.

- Default Chains
    - INPUT - Packets recieved on the network interface that are destined for the machine.
    - OUTPUT - Packets originating on the machine that are destined for other systems.
    - FORWARD - Packets recieved on the network interface that are destined for another system.


- Each rule has two things:
    - Specification of a type of packet. Criteria for matching.
    - A routing to a TARGET (Possibly another chain, or DROP, ACCEPT, REJECT and other built-in targets)

- Default Policy: Can be set on INPUT, OUTPUT, and FORWARD
    - Common Options
        - ACCEPT - The packet is allowed through the filter.
        - DROP - The packet processing ceases, the packet stops.
        - Reject - Drop the packet and inform the remote machine.

- Adding a Rule
    - Protocol -p (Usually TCP or UDP)
    - Destination port number --dport
    - Source port number --sport
    - Source Address / Range -s
    - Destination Address / Range -d

- State Options
    - NEW - A packet which creates a new connection.
    - ESTABLISHED - A packet which belongs to an already established connection.
    - RELATED - A packet that is related to an already established communication.
    - INVALID - An unidentified packet.
{{% /panel %}}


{{% panel="Building IPTables Firewall" header=" Building IPTables Firewall" theme="default" %}}
```bash
# Block all then allow what is needed. Don't do this on a remote machine!!!!!
# Syntax: iptables -P chain target
iptables -P INPUT DROP
```
```bash
# SSH through any source address (0/0 shorthand for any address)
iptables -A INPUT -s 0/0 -p tcp --dport 22 -j ACCEPT
# You can add --syn flag to only allow SYN packets
iptables -A INPUT -s 0/0 -p tcp --dport 22 --syn -j ACCEPT
```
```bash
# Allow related and established packets through.
iptables -A INPUT -s 0/0 -m state --state RELATED,ESTABLISHED -j ACCEPT
```
```bash
# Flush out rules (Carefull!)
iptables -F 
```

```bash
# Rate limiting (3 Per minute burst)
iptables -A INPUT -p TCP --dport 22 --syn -m limit --limit 3/m \ --limit-burst 1 -j ACCEPT
```
{{% /panel %}}

```bash
# Example bash script

# Flush all rules from all chains
iptables -F

# Drop all packets not explicitly accepted 
iptables -p  INPUT DROP

# Accept packets that are part of communication already
iptables -A INPUT -s 0/0 -m state --state RELATED, ESTABLISHED, -j ACCEPT

# Accept syn packets from SSH
iptables -A INPUT -s 0/0 -p tcp --syn --dport 22 -j ACCEPT
```
