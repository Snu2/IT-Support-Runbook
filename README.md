# IT Support Troubleshooting Runbook

A practical reference guide documenting common IT support and networking issues, their root causes, and step-by-step resolution procedures — built the way real support teams document their workflows.

## Purpose

This runbook serves as a quick-reference guide for diagnosing and resolving the most frequent issues faced in IT support and networking environments. It's designed to speed up troubleshooting by providing a clear, repeatable process for each problem.

---

## Common Issues & Resolutions

### 1. User Cannot Connect to Wi-Fi

**Symptoms:** Device shows "no internet" or fails to connect to the wireless network.

**Diagnosis steps:**
1. Confirm the correct network (SSID) is selected
2. Verify the Wi-Fi password is correct
3. Check if other devices can connect to the same network
4. Restart the router/access point
5. Forget the network on the device and reconnect
6. Check if DHCP is assigning an IP address correctly

**Resolution:** If steps 1–5 don't resolve it, check the router's DHCP pool for available addresses, or manually assign a static IP to test connectivity.

---

### 2. Slow Network Performance

**Symptoms:** Pages load slowly, file transfers take longer than expected, video calls lag.

**Diagnosis steps:**
1. Run `ping` to test basic connectivity and latency
2. Run `tracert` (Windows) or `traceroute` (Mac/Linux) to identify where delays occur
3. Check bandwidth usage — are multiple devices/users saturating the connection?
4. Test with a wired connection to rule out Wi-Fi interference
5. Check for background applications consuming bandwidth

**Resolution:** Identify the bottleneck (ISP, router, local network congestion) and address accordingly — may require QoS configuration or upgrading bandwidth.

---

### 3. Network Printer Not Printing

**Symptoms:** Print jobs stuck in queue, printer shows offline, or nothing happens when printing.

**Diagnosis steps:**
1. Confirm the printer is powered on and connected to the network
2. Ping the printer's IP address to confirm it's reachable
3. Check the print queue for stuck jobs — clear and retry
4. Verify the correct printer driver is installed
5. Restart the print spooler service (Windows: `services.msc` → Print Spooler)

**Resolution:** Reinstall printer drivers if outdated, or re-add the printer using its correct IP/hostname.

---

### 4. Cannot Access a Specific Website or Service

**Symptoms:** One site/service fails to load while others work fine.

**Diagnosis steps:**
1. Try accessing the site from a different device/network to isolate the issue
2. Run `nslookup <domain>` to check DNS resolution
3. Clear DNS cache (`ipconfig /flushdns` on Windows)
4. Check if a firewall or proxy is blocking the site
5. Test using a different DNS server (e.g., 8.8.8.8)

**Resolution:** If DNS resolution fails, update DNS settings. If blocked by firewall/proxy, escalate to network admin for a policy review.

---

### 5. VPN Connection Issues

**Symptoms:** VPN fails to connect, disconnects randomly, or blocks internet access once connected.

**Diagnosis steps:**
1. Verify credentials and VPN server address are correct
2. Check internet connectivity without VPN first
3. Restart the VPN client
4. Check for conflicting network adapters or firewall rules
5. Review VPN logs for specific error codes

**Resolution:** Reinstall VPN client if corrupted, or contact VPN provider/admin if the issue is server-side.

---

## Essential Networking Commands

| Command | Purpose |
|---|---|
| `ping <host>` | Tests basic connectivity and measures latency to a host |
| `ipconfig` / `ifconfig` | Displays network configuration (IP, subnet, gateway) |
| `tracert` / `traceroute` | Shows the path packets take to reach a destination, useful for locating delays |
| `nslookup <domain>` | Queries DNS to resolve a domain name to an IP address |
| `netstat` | Displays active network connections and listening ports |
| `ipconfig /flushdns` | Clears the local DNS cache |

---

## Key Networking Concepts

- **DNS (Domain Name System):** Translates human-readable domain names (e.g., google.com) into IP addresses.
- **DHCP (Dynamic Host Configuration Protocol):** Automatically assigns IP addresses to devices on a network.
- **Subnet:** A logical subdivision of a network, used to organize and manage IP address ranges.
- **Gateway:** The device (usually a router) that connects a local network to external networks like the internet.
- **Firewall:** A security system that monitors and controls incoming/outgoing network traffic based on defined rules.

---

## About This Project

This runbook was built as a hands-on learning project to document real-world IT support troubleshooting workflows. It reflects a structured, methodical approach to diagnosing and resolving common technical issues.

*Continuously updated as new issues and solutions are documented.*
