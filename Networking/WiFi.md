# Wi-Fi Networking

Reference guide covering Wi-Fi fundamentals, standards, security, and how wireless networks operate.

---

## How Wi-Fi Works

Wi-Fi allows devices to connect to a network using radio waves instead of cables. A wireless access point (AP) or router broadcasts a signal (SSID) that devices can detect and connect to, provided they have the correct credentials.

Key components:
- **SSID (Service Set Identifier):** The network's name, broadcast so devices can find it.
- **Access Point (AP):** The hardware device that creates the wireless network.
- **Frequency Bands:** Wi-Fi operates on 2.4GHz and 5GHz (and increasingly 6GHz with Wi-Fi 6E).
  - 2.4GHz: Longer range, more interference, slower speeds.
  - 5GHz: Shorter range, less interference, faster speeds.

---

## Wi-Fi Standards (802.11)

| Standard | Common Name | Max Speed (theoretical) | Band |
|---|---|---|---|
| 802.11n | Wi-Fi 4 | 600 Mbps | 2.4/5GHz |
| 802.11ac | Wi-Fi 5 | 3.5 Gbps | 5GHz |
| 802.11ax | Wi-Fi 6 | 9.6 Gbps | 2.4/5GHz |
| 802.11ax (6E) | Wi-Fi 6E | 9.6 Gbps | 6GHz |

Newer standards generally offer better speed, capacity for more devices, and improved efficiency — but require compatible hardware on both the router and device.

---

## Wi-Fi Security Protocols

| Protocol | Security Level | Notes |
|---|---|---|
| WEP | Very weak (deprecated) | Easily cracked, should never be used |
| WPA | Weak (deprecated) | Improved over WEP but still vulnerable |
| WPA2 | Strong | Industry standard for years, uses AES encryption |
| WPA3 | Strongest | Current standard, resistant to offline password attacks |

**Best practice:** Always use WPA2 or WPA3 with a strong, unique password. Avoid open (unsecured) networks for anything sensitive.

---

## Common Wi-Fi Concepts

- **Channel:** A specific frequency range within a band. Routers can be set to specific channels to avoid interference from neighboring networks.
- **Signal Strength (RSSI):** Measured in dBm; closer to 0 is stronger (e.g., -50 dBm is excellent, -80 dBm is poor).
- **Roaming:** The ability of a device to switch between access points seamlessly in a network with multiple APs (common in offices).
- **Guest Network:** An isolated network that gives visitors internet access without exposing the main network's devices.
- **MAC Filtering:** Restricting network access based on device hardware addresses — an added layer of control, though not foolproof.

---

## Related

- See [Troubleshooting/WiFi.md](../Troubleshooting/WiFi.md) for step-by-step diagnosis of connectivity issues.
- See [Commands/Network.md](../Commands/Network.md) for relevant command-line tools.
