# Module 3: Wireless and Mobile Networks

## Key Concepts

### Why Wireless?
Wireless networks use **radio waves** to transmit data — no physical cable needed. This makes them flexible but also more exposed to attacks since signals travel through open air.

### Wi-Fi Standards (IEEE 802.11)
| Standard | Frequency | Max Speed | Notes |
|----------|-----------|-----------|-------|
| 802.11b | 2.4 GHz | 11 Mbps | Old, rarely used |
| 802.11g | 2.4 GHz | 54 Mbps | Common in older devices |
| 802.11n | 2.4/5 GHz | 600 Mbps | Dual band |
| 802.11ac | 5 GHz | 3.5 Gbps | Common today (Wi-Fi 5) |
| 802.11ax | 2.4/5/6 GHz | 9.6 Gbps | Latest (Wi-Fi 6) |

### 2.4 GHz vs 5 GHz
| | 2.4 GHz | 5 GHz |
|--|---------|-------|
| Range | Longer | Shorter |
| Speed | Slower | Faster |
| Interference | More (used by microwaves, Bluetooth) | Less |
| Wall penetration | Better | Worse |

### Wireless Network Types
- **WLAN** — Wireless LAN (Wi-Fi in home/office)
- **WPAN** — Wireless PAN (Bluetooth, Zigbee — short range, IoT)
- **WMAN** — Wireless MAN (WiMAX — city range)
- **WWAN** — Wireless WAN (4G/5G cellular)

### Cellular Networks
| Generation | Key Feature |
|-----------|-------------|
| 3G | First mobile internet |
| 4G/LTE | Fast mobile broadband |
| 5G | Ultra-low latency, massive IoT support |

### Bluetooth
- Short range (~10m standard, ~100m Class 1)
- Used for PANs — headsets, keyboards, IoT sensors
- Versions: Bluetooth Classic vs **Bluetooth Low Energy (BLE)** — BLE is dominant in IoT

### Zigbee & Z-Wave
- Low power, mesh networking protocols
- Heavily used in **smart home IoT** (smart bulbs, door sensors, thermostats)
- Operate on 2.4 GHz (Zigbee) and sub-1GHz (Z-Wave)

---

## IoT/Hardware Pentesting Relevance
- **Wi-Fi attacks** — WPA2 handshake capture, PMKID attack, evil twin AP
- **BLE attacks** — BLE sniffing, GATT enumeration, BLE MITM — very common in IoT pentesting
- **Zigbee attacks** — Zigbee sniffing with tools like HackRF or TI CC2531 sniffer
- 2.4 GHz band is extremely crowded — makes **signal analysis and jamming** easier to study
- 5G's role in massive IoT (mMTC) makes cellular security increasingly important
