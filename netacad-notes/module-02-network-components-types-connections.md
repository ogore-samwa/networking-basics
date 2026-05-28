# Module 2: Network Components, Types, and Connections

## Key Concepts

### End Devices
End devices are where data originates or is received:
- Computers, laptops, smartphones
- Printers, IP cameras, smart TVs
- IoT sensors, actuators, embedded controllers

Each end device has a **Network Interface Card (NIC)** — hardware that connects the device to the network.

### Intermediary Devices
Devices that forward and manage data between end devices:

| Device | Role |
|--------|------|
| **Switch** | Connects devices within a LAN, forwards frames using MAC addresses |
| **Router** | Connects different networks, forwards packets using IP addresses |
| **Wireless Access Point (WAP)** | Connects wireless devices to a wired network |
| **Firewall** | Filters traffic based on security rules |
| **Modem** | Converts signals between your network and ISP |

### Network Media Types
The physical path data travels on:

| Media | Signal Type | Example |
|-------|------------|---------|
| Copper (UTP/STP) | Electrical signals | Ethernet cable |
| Fiber Optic | Light pulses | ISP backbone links |
| Wireless | Radio waves | Wi-Fi, Bluetooth, Zigbee |

### Network Types
- **Client-Server** — dedicated servers provide services; clients request them
- **Peer-to-Peer (P2P)** — devices share resources directly without a central server

### ISP Connection Types
- **DSL** — uses phone lines
- **Cable** — uses coaxial TV lines
- **Fiber** — uses fiber optic cables (fastest)
- **Cellular** — uses mobile towers (4G/5G)
- **Satellite** — used in remote areas

---

## IoT/Hardware Pentesting Relevance
- Knowing intermediary devices helps identify **network entry points** during a pentest
- Switches and routers are common targets — misconfigured ones expose the whole network
- Wireless media (radio waves) can be **sniffed passively** — no physical access needed
- IoT devices often connect via WAPs, making the access point a critical attack surface
