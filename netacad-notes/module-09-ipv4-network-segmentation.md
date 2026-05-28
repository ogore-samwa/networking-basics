# Module 9: IPv4 and Network Segmentation

## Key Concepts

### Why Segment a Network?
Segmenting a network means dividing it into smaller sub-networks (**subnets**). Benefits:
- **Performance** — less broadcast traffic, less congestion
- **Security** — isolates sensitive devices from the rest of the network
- **Organization** — group devices by function or department

### Subnet Mask
The **subnet mask** tells a device which part of an IP address is the network and which is the host.

Written in two ways:
- **Dotted decimal:** `255.255.255.0`
- **CIDR notation:** `/24` (means 24 bits are the network portion)

Common subnet masks:
| CIDR | Subnet Mask | # of Hosts |
|------|-------------|------------|
| /8 | 255.0.0.0 | 16,777,214 |
| /16 | 255.255.0.0 | 65,534 |
| /24 | 255.255.255.0 | 254 |
| /25 | 255.255.255.128 | 126 |
| /26 | 255.255.255.192 | 62 |
| /30 | 255.255.255.252 | 2 |

### Calculating Subnets
For any subnet:
- **Network address** — first address (all host bits = 0) — not assignable
- **Broadcast address** — last address (all host bits = 1) — not assignable
- **Usable hosts** = 2ⁿ - 2 (where n = number of host bits)

Example — 192.168.1.0 /24:
```
Network address:   192.168.1.0
First usable host: 192.168.1.1
Last usable host:  192.168.1.254
Broadcast:         192.168.1.255
Total usable:      254 hosts
```

### Subnetting Example
You have `192.168.1.0 /24` and need 4 subnets:
- Borrow 2 bits from the host portion → /26
- Each subnet has 64 addresses, 62 usable

| Subnet | Network Address | Usable Range | Broadcast |
|--------|----------------|--------------|-----------|
| 1 | 192.168.1.0 | .1 – .62 | .63 |
| 2 | 192.168.1.64 | .65 – .126 | .127 |
| 3 | 192.168.1.128 | .129 – .190 | .191 |
| 4 | 192.168.1.192 | .193 – .254 | .255 |

### Private vs Public IP Addresses
| Type | Range | Use |
|------|-------|-----|
| Private | 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16 | Internal networks only |
| Public | Everything else | Routable on the internet |

Private addresses are **not routable on the internet** — NAT translates them to public IPs.

### IPv6 — Brief Overview
IPv4 is running out of addresses (only ~4.3 billion). **IPv6** solves this:
- 128-bit addresses — virtually unlimited
- Written in hexadecimal: `2001:0db8:85a3::8a2e:0370:7334`
- No need for NAT
- Built-in security features (IPSec)

---

## IoT/Hardware Pentesting Relevance
- **Subnet scanning** — knowing the subnet lets you scan all hosts: `nmap 192.168.1.0/24`
- **Network segmentation as defense** — IoT devices should be on an isolated VLAN/subnet, not the same as your main devices. Pentests often find they aren't.
- **VLAN hopping** — attack that jumps between subnets/VLANs when segmentation is misconfigured
- Private IP ranges tell you you're inside a NAT network — relevant when pivoting during a pentest
- IPv6 is increasingly used in IoT — many pentesters overlook it, leaving devices exposed
