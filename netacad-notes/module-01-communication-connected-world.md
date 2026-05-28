# Module 1: Communication in a Connected World

## Key Concepts

### What is a Network?
A network is two or more devices connected together to share resources and communicate. Networks can be as small as two computers or as large as the internet.

### Types of Networks by Size
| Type | Full Name | Scope |
|------|-----------|-------|
| PAN | Personal Area Network | Around a person (Bluetooth, USB) |
| LAN | Local Area Network | Home, office, school building |
| MAN | Metropolitan Area Network | City-wide |
| WAN | Wide Area Network | Country or worldwide (e.g. the Internet) |

### Network Components
Every network needs:
- **End devices** — the source or destination of data (PC, phone, printer, IoT sensor)
- **Intermediary devices** — move data between end devices (routers, switches, access points)
- **Media** — the path data travels on (copper cable, fiber optic, wireless/radio waves)

### Data Transmission
Data travels across networks in small chunks called **packets**. Breaking data into packets allows:
- Multiple devices to share the same network path
- Faster error detection and retransmission
- More efficient use of bandwidth

### Bandwidth vs Throughput
- **Bandwidth** — the maximum capacity of a link (e.g. 100 Mbps)
- **Throughput** — the actual data transferred in practice (always less than bandwidth due to overhead, interference, traffic)

### Network Representations
Networks are drawn as **topology diagrams**:
- **Physical topology** — shows actual physical layout and device locations
- **Logical topology** — shows how data flows, IP addresses, device roles

---

## IoT/Hardware Pentesting Relevance
- Every IoT device is an **end device** on a network — understanding how end devices communicate is the foundation for attacking them
- PANs (Bluetooth, Zigbee, Z-Wave) are common IoT attack surfaces
- Packet-based communication means traffic can be **captured and analyzed** with tools like Wireshark
