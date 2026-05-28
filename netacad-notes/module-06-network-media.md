# Module 6: Network Media

## Key Concepts

### Three Types of Network Media
Data can travel on three types of media:
1. **Copper cable** — electrical signals
2. **Fiber optic cable** — light pulses
3. **Wireless** — radio waves

---

### 1. Copper Cable
Most common and cheapest. Data is transmitted as **electrical signals**.

#### Types of Copper Cable

**UTP (Unshielded Twisted Pair)**
- Most common network cable
- 4 pairs of twisted copper wires
- Twisting reduces **electromagnetic interference (EMI)**
- Used for Ethernet (RJ-45 connector)

**STP (Shielded Twisted Pair)**
- Like UTP but with a metallic shield around the pairs
- Better EMI protection — used in industrial environments
- More expensive and harder to install

**Coaxial Cable**
- Single copper conductor with insulation and a braided shield
- Used for cable TV and older cable internet connections
- Still used in some CCTV systems

#### UTP Cable Categories
| Category | Max Speed | Max Length | Use |
|----------|-----------|------------|-----|
| Cat 5e | 1 Gbps | 100m | Common LAN |
| Cat 6 | 10 Gbps | 55m | Modern LAN |
| Cat 6a | 10 Gbps | 100m | Data centers |

#### Copper Cable Limitations
- **Attenuation** — signal weakens over distance (max 100m for UTP)
- **EMI/RFI** — interference from motors, fluorescent lights, other cables
- **Crosstalk** — signal from one wire bleeds into adjacent wire

---

### 2. Fiber Optic Cable
Transmits data as **pulses of light** through a glass or plastic core.

#### Types
| Type | Core Size | Distance | Use |
|------|-----------|----------|-----|
| SMF (Single-Mode Fiber) | Small (~9μm) | Kilometers | ISP backbone, long distance |
| MMF (Multi-Mode Fiber) | Large (~50-62.5μm) | Up to 550m | Data centers, campus networks |

#### Advantages over Copper
- Much longer distances
- Immune to EMI/RFI
- Higher bandwidth
- Cannot be tapped by induction (more secure physically)

#### Disadvantages
- Expensive
- Fragile — difficult to install and terminate
- Requires specialized equipment

---

### 3. Wireless Media
Transmits data as **radio waves** through open air.

- No physical cable needed
- Subject to interference from walls, other devices, weather
- Signal can be intercepted by anyone in range — security critical
- Standards: 802.11 (Wi-Fi), Bluetooth, Zigbee, cellular

---

## IoT/Hardware Pentesting Relevance
- **Copper cables can be tapped** — crocodile clips on UTP or inductive taps on coax are physical layer attacks
- **EMI attacks** — introducing interference to disrupt communication or extract data (relates to your EE background)
- Fiber is harder to tap physically but not impossible — fiber tapping tools exist
- Wireless is the **easiest to attack** — no physical access needed, just be in radio range
- Understanding cable types helps during **physical pentests** — identifying what cable is used tells you the likely network speed and topology
