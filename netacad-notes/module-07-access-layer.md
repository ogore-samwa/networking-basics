# Module 7: The Access Layer

## Key Concepts

### What is the Access Layer?
The **access layer** is where end devices connect to the network. It is the bottom layer of a three-tier network design:
- **Access layer** — connects end devices (PCs, phones, IoT devices)
- **Distribution layer** — aggregates access layer connections
- **Core layer** — high-speed backbone

In home/small networks, all three layers are often collapsed into one device (the router/switch).

### Ethernet
**Ethernet** is the dominant wired LAN technology. Defined by **IEEE 802.3**.

- Operates at the **Network Access layer** of TCP/IP
- Devices communicate using **MAC addresses**
- Data is sent in **frames**

### MAC Addresses
- **MAC = Media Access Control**
- A unique 48-bit (6-byte) hardware address burned into every NIC at the factory
- Written as: `AA:BB:CC:DD:EE:FF` (hexadecimal)
- First 3 bytes = **OUI (Organizationally Unique Identifier)** — identifies the manufacturer
- Last 3 bytes = unique device identifier

Example: `B8:27:EB:xx:xx:xx` → Raspberry Pi Foundation

### How a Switch Works
A switch builds a **MAC address table** (also called CAM table):
1. A frame arrives on a port
2. Switch records the **source MAC** and the **port** it came from
3. Switch looks up the **destination MAC** in its table
4. If found → forwards frame only to that port (**unicast**)
5. If not found → sends frame to **all ports** (**flooding**)

This is more efficient than older hubs which sent everything to all ports.

### Frame Structure
An Ethernet frame contains:
| Field | Size | Purpose |
|-------|------|---------|
| Preamble | 8 bytes | Signals start of frame |
| Destination MAC | 6 bytes | Where the frame is going |
| Source MAC | 6 bytes | Where the frame came from |
| EtherType | 2 bytes | Protocol inside (e.g. IPv4, IPv6, ARP) |
| Data/Payload | 46-1500 bytes | The actual data |
| FCS (CRC) | 4 bytes | Error checking |

### ARP (Address Resolution Protocol)
- Translates **IP addresses → MAC addresses**
- When a device knows the IP but not the MAC of the destination, it sends an **ARP request** (broadcast)
- The device with that IP replies with its MAC address
- Result is stored in the **ARP cache**

---

## IoT/Hardware Pentesting Relevance
- **MAC spoofing** — changing your MAC address to impersonate another device, bypass MAC filtering
- **ARP poisoning / ARP spoofing** — sending fake ARP replies to redirect traffic through your machine (MITM attack)
- **CAM table overflow** — flooding a switch with fake MACs fills the table, causing it to flood all traffic like a hub (enables sniffing)
- OUI lookup reveals device manufacturer — useful in **IoT device fingerprinting** during recon
- Wireshark shows full Ethernet frames — you can see source/destination MACs, EtherType, and payload
