# Troubleshooting: Wi-Fi Connectivity

Step-by-step diagnosis and resolution for Wi-Fi connection issues.

> See [Networking/WiFi.md](../Networking/WiFi.md) for background on how Wi-Fi works.

---

## Symptom: Device Cannot Connect to Wi-Fi

**Possible causes:** Wrong password, incorrect network selected, router issue, DHCP failure, driver issue.

### Diagnosis Steps

1. **Confirm the correct network (SSID) is selected** — especially in environments with similarly named networks (e.g., a 2.4GHz and 5GHz version of the same network).
2. **Verify the Wi-Fi password is correct** — check for case sensitivity and recently changed passwords.
3. **Check if other devices can connect** to the same network. If yes, the issue is device-specific; if no, the issue is likely the router/AP.
4. **Restart the router/access point** — resolves a large share of transient connectivity issues.
5. **Forget the network on the device and reconnect** — clears any corrupted saved network profile.
6. **Check if DHCP is assigning an IP address correctly** — run `ipconfig` (Windows) or `ip a` (Linux) to confirm a valid IP was received, not an APIPA address (169.254.x.x).

### Resolution

- If steps 1–5 don't resolve it, check the router's DHCP scope for available addresses (see [Networking/DHCP.md](../Networking/DHCP.md)).
- If only one device is affected, update or reinstall the Wi-Fi adapter driver.
- If the issue started after a router firmware update, check for known issues with that firmware version.

---

## Symptom: Wi-Fi Connects but Frequently Drops

**Possible causes:** Signal interference, weak signal strength, outdated router firmware, power-saving settings.

### Diagnosis Steps

1. Check signal strength (RSSI) — move closer to the AP to rule out range issues.
2. Check for interference sources (microwaves, other routers on the same channel, thick walls).
3. Disable Wi-Fi adapter power-saving mode on the device (common cause of intermittent drops on laptops).
4. Update router firmware if outdated.

### Resolution

- Switch to a less congested channel or the 5GHz band if available.
- If multiple devices are affected, consider whether the AP itself needs replacement or firmware update.

---

## Related

- [Networking/WiFi.md](../Networking/WiFi.md) — Wi-Fi fundamentals and security protocols
- [Networking/DHCP.md](../Networking/DHCP.md) — IP assignment issues
- [Commands/Network.md](../Commands/Network.md) — Diagnostic commands referenced above
