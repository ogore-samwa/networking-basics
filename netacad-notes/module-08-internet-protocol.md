# Module 8: The Internet Protocol

## Key Concepts

### What is IP?
The **Internet Protocol (IP)** is responsible for **addressing and routing** packets across networks. It operates at the **Internet layer** of the TCP/IP model.

IP is **connectionless** — it doesn't establish a connection before sending data and doesn't guarantee delivery. That's TCP's job.

### IPv4 Addresses
- 32-bit address written in **dotted decimal** notation
- Format: four **octets** separated by dots
- Example: `192.168.1.105`
- Each octet is 8 bits → values from 0 to 255

### IPv4 Address Structure
Every IPv4 address has two parts:
- **Network portion** — identifies the network
- **Host portion** — identifies the specific device on that network

The **subnet mask** determines which part is network and which is host.

Example:
```
IP Address:   192.168.1.105
Subnet Mask:  255.255.255.0
Network:      192.168.1.0
Host:         .105
```

### Types of IPv4 Addresses
| Type | Description | Example |
|------|-------------|---------|
| **Unicast** | One sender → one specific receiver | 192.168.1.10 |
| **Broadcast** | One sender → all devices on network | 192.168.1.255 |
| **Multicast** | One sender → a group of receivers | 224.0.0.x |

### Special IPv4 Addresses
| Address | Purpose |
|---------|---------|
| 127.0.0.1 | Loopback — refers to yourself (localhost) |
| 0.0.0.0 | Default route / unspecified |
| 255.255.255.255 | Limited broadcast (all devices on local network) |

### Default Gateway
- The **default gateway** is the router's IP address on your local network
- When a device wants to send data outside its network, it sends it to the default gateway
- The router then forwards it toward the destination

### DNS (Domain Name System)
- Translates **human-readable names → IP addresses**
- Example: `google.com` → `142.250.185.46`
- Without DNS you'd have to memorize IP addresses for every website
- DNS operates on **port 53**

### How Data Travels: End-to-End
1. Device checks: is the destination on my network or a different network?
2. **Same network** → sends directly using MAC address (ARP first if needed)
3. **Different network** → sends to default gateway (router)
4. Router examines destination IP and forwards packet toward destination
5. Process repeats at each router until packet reaches destination

---

## IoT/Hardware Pentesting Relevance
- **IP spoofing** — sending packets with a fake source IP address
- **ICMP (ping) reconnaissance** — using ping sweeps to discover live hosts on a network (Nmap uses this)
- **DNS attacks** — DNS poisoning, DNS hijacking redirect traffic to malicious servers
- Knowing the default gateway is step one in **network mapping** during a pentest
- Loopback (127.0.0.1) is used heavily in testing — understanding it helps when analyzing device firmware and local services
- IoT devices with hardcoded IPs or DNS settings are a common misconfiguration vulnerability
