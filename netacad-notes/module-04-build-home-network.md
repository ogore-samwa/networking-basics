# Module 4: Build a Home Network

## Key Concepts

### Home Network Devices
A typical home network includes:
- **Modem** — connects to ISP, brings internet into the home
- **Router** — distributes internet to all devices, assigns IP addresses via DHCP
- **Switch** — expands wired connections (not always present in small home networks)
- **Wireless Access Point (WAP)** — provides Wi-Fi (often built into the router)
- **End devices** — phones, laptops, smart TVs, IoT devices

### Home Router Functions
A home router typically does all of this in one box:
- **Routing** — forwards traffic between your LAN and the internet (WAN)
- **Switching** — connects wired devices via ethernet ports
- **DHCP server** — automatically assigns IP addresses to devices
- **NAT** — hides all internal IPs behind one public IP
- **Firewall** — basic traffic filtering
- **WAP** — provides Wi-Fi

### DHCP (Dynamic Host Configuration Protocol)
- Automatically assigns IP address, subnet mask, default gateway, and DNS to devices
- Without DHCP you'd have to manually configure every device
- Home router is usually the DHCP server

### NAT (Network Address Translation)
- Your ISP gives you **one public IP address**
- NAT lets all your home devices share that one IP
- Internally each device gets a **private IP** (e.g. 192.168.1.x)
- NAT translates between private and public IPs

### Private IP Address Ranges
| Range | Common Use |
|-------|-----------|
| 192.168.0.0 – 192.168.255.255 | Home networks |
| 10.0.0.0 – 10.255.255.255 | Enterprise networks |
| 172.16.0.0 – 172.31.255.255 | Less common |

### Wireless Security Standards
| Standard | Security Level | Notes |
|----------|---------------|-------|
| WEP | Very weak | Broken, never use |
| WPA | Weak | Deprecated |
| WPA2 | Strong | Current standard |
| WPA3 | Strongest | Latest, growing adoption |

---

## IoT/Hardware Pentesting Relevance
- Home routers are **primary targets** in IoT pentesting — they control all traffic
- Default credentials on routers are a common vulnerability (admin/admin, admin/password)
- **NAT traversal** is relevant when attacking devices behind NAT
- WEP/WPA networks can be cracked — WPA2 requires capturing the 4-way handshake
- IoT devices often sit on the same network as sensitive devices — lateral movement risk
