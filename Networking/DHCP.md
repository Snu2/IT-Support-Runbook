# DHCP (Dynamic Host Configuration Protocol)

Reference guide covering how DHCP works, the lease process, and common configuration concepts.

---

## How DHCP Works

DHCP automatically assigns IP addresses and other network configuration details to devices when they join a network, removing the need to manually configure each device.

**The DORA process (DHCP lease process):**
1. **Discover:** The device broadcasts a request looking for a DHCP server
2. **Offer:** The DHCP server responds with an offered IP address and configuration
3. **Request:** The device requests to use the offered IP address
4. **Acknowledge:** The DHCP server confirms and finalizes the lease

This process typically completes in a fraction of a second when connecting to a network.

---

## What DHCP Assigns

Beyond just an IP address, a DHCP server typically provides:

| Parameter | Purpose |
|---|---|
| IP Address | The device's unique address on the network |
| Subnet Mask | Defines the network's address range |
| Default Gateway | The router used to reach other networks/the internet |
| DNS Servers | Where the device sends domain name lookups |
| Lease Time | How long the device can use the assigned IP before renewal |

---

## Key DHCP Concepts

- **DHCP Scope:** The range of IP addresses a DHCP server is allowed to hand out (e.g., 192.168.1.100–192.168.1.200).
- **Lease Time:** The duration an IP assignment is valid before the device must renew it. Short leases suit busy networks with many devices; long leases reduce renewal traffic.
- **DHCP Reservation:** A fixed IP address assigned to a specific device (by MAC address) so it always receives the same address, useful for printers or servers.
- **DHCP Relay:** Allows DHCP requests to cross between different network segments when the DHCP server isn't on the same local network.
- **APIPA (Automatic Private IP Addressing):** If a device can't reach a DHCP server, it self-assigns an address in the 169.254.x.x range — a strong sign of a DHCP connectivity problem.

---

## Common DHCP Issues

- **Device gets no IP address / APIPA address (169.254.x.x):** Usually means the device couldn't reach the DHCP server — check cabling, Wi-Fi connection, or whether the DHCP service is running.
- **IP address conflicts:** Two devices assigned the same static or leased IP, often due to manual static IPs overlapping the DHCP scope.
- **Scope exhaustion:** No IPs left to assign because the scope is full — common on networks with many devices and short lease times.

---

## Related

- See [Troubleshooting/WiFi.md](../Troubleshooting/WiFi.md) for connectivity issues that may involve DHCP.
- See [Commands/Network.md](../Commands/Network.md) for relevant command-line tools (`ipconfig /release`, `ipconfig /renew`).
