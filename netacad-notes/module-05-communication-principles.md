# Module 5: Communication Principles

## Key Concepts

### Rules of Communication
All communication — human or digital — needs:
1. **A sender** — originates the message
2. **A receiver** — receives the message
3. **A medium** — the channel the message travels on
4. **A message** — the actual data/information
5. **Agreed-upon rules (protocols)** — both sides must speak the same language

### What is a Protocol?
A **protocol** is a set of rules that defines how communication happens. Examples:
- **HTTP** — how web browsers and servers talk
- **TCP** — how data is reliably sent and received
- **IP** — how packets are addressed and routed
- **Ethernet** — how devices communicate on a LAN

### Protocol Suites
Protocols work together in **suites (stacks)**:
- **TCP/IP suite** — the foundation of the internet
- Protocols in a suite each handle a different layer of communication

### The TCP/IP Model (4 Layers)
| Layer | Name | Function | Example Protocols |
|-------|------|----------|------------------|
| 4 | Application | User-facing services | HTTP, FTP, DNS, DHCP |
| 3 | Transport | Reliable/unreliable delivery | TCP, UDP |
| 2 | Internet | Addressing and routing | IP, ICMP |
| 1 | Network Access | Physical transmission | Ethernet, Wi-Fi |

### TCP vs UDP
| | TCP | UDP |
|--|-----|-----|
| Connection | Connection-oriented | Connectionless |
| Reliability | Guaranteed delivery | No guarantee |
| Speed | Slower | Faster |
| Use case | Web, email, file transfer | Video streaming, VoIP, DNS, IoT |

### Encapsulation
As data moves **down** the TCP/IP stack, each layer adds its own **header** (and sometimes trailer):
- Application data → **Segment** (Transport adds TCP/UDP header)
- Segment → **Packet** (Internet adds IP header)
- Packet → **Frame** (Network Access adds Ethernet header + trailer)
- Frame → **Bits** (physical transmission)

On the receiving end, each layer **strips** its header — this is called **decapsulation**.

### PDUs (Protocol Data Units)
Each layer has a name for its data unit:
| Layer | PDU Name |
|-------|---------|
| Application | Data |
| Transport | Segment |
| Internet | Packet |
| Network Access | Frame |
| Physical | Bits |

---

## IoT/Hardware Pentesting Relevance
- Understanding encapsulation is essential for **packet analysis with Wireshark** — you read each layer's headers
- **UDP** is dominant in IoT — lightweight, low power, fast — but no built-in security
- Protocol vulnerabilities exist at every layer — knowing the layer helps pinpoint where an attack occurs
- ICMP (ping) is used in **network reconnaissance** — the first step of any pentest
