# Nmap

Reference guide covering what Nmap is, how it's used, and key concepts for network scanning and discovery.

---

## What Is Nmap

Nmap ("Network Mapper") is a free, open-source tool used to discover devices on a network, identify open ports, detect running services, and assess basic security posture. It's one of the most widely used tools in IT support, networking, and cybersecurity for understanding what's actually present and accessible on a network.

Unlike Wireshark (which captures traffic passing through), Nmap actively probes hosts to gather information — making it a discovery and assessment tool rather than a passive monitoring one.

---

## Core Concepts

- **Host Discovery:** Identifying which devices on a network are currently online and reachable.
- **Port Scanning:** Checking which ports on a device are open, closed, or filtered — revealing what services might be running.
- **Service/Version Detection:** Identifying not just that a port is open, but what specific service and version is running on it.
- **OS Detection:** Nmap can often infer a target's operating system based on how it responds to certain probes.

---

## Common Scan Types

| Scan Type | Flag | Purpose |
|---|---|---|
| Ping Scan | `-sn` | Discovers which hosts are online without scanning ports |
| TCP SYN Scan | `-sS` | Fast, stealthy scan of open TCP ports (default for privileged users) |
| TCP Connect Scan | `-sT` | Full TCP connection scan, used when SYN scan isn't possible |
| UDP Scan | `-sU` | Scans UDP ports (slower than TCP scanning) |
| Service Version Scan | `-sV` | Detects service and version info on open ports |
| OS Detection | `-O` | Attempts to identify the target's operating system |
| Aggressive Scan | `-A` | Combines OS detection, version detection, script scanning, and traceroute |

---

## Common Command Examples

| Command | Purpose |
|---|---|
| `nmap 192.168.1.1` | Basic scan of a single host |
| `nmap 192.168.1.0/24` | Scan an entire subnet |
| `nmap -p 80,443 192.168.1.1` | Scan specific ports only |
| `nmap -p- 192.168.1.1` | Scan all 65,535 ports |
| `nmap -sV -O 192.168.1.1` | Detect services and OS on a target |

---

## Key Concepts

- **Open vs. Closed vs. Filtered:** Open means a service is actively listening; closed means no service is listening but the host responded; filtered means no response was received, often due to a firewall.
- **Stealth Scanning:** Techniques (like SYN scans) designed to be less detectable by not completing a full TCP handshake — useful for minimizing footprint during authorized assessments.
- **NSE (Nmap Scripting Engine):** Allows running scripts for more advanced tasks like vulnerability detection, though this moves into more specialized security testing territory.

---

## Common Use Cases

- **Network inventory:** Quickly identifying all active devices on a network segment, useful when documentation is outdated or missing.
- **Verifying firewall rules:** Confirming that only intended ports are open/reachable from a given location.
- **Troubleshooting service availability:** Checking whether a specific service (e.g., a web server on port 80/443) is actually reachable before digging deeper into application-level issues.

---

## Important: Authorization

Scanning networks or devices without explicit permission is illegal in most jurisdictions and considered unauthorized access, even without malicious intent. Nmap should only be used on networks/devices you own or have documented authorization to test — this is a core professional and ethical standard in IT and security work.

---

## Related

- See [Tools/Wireshark.md](Wireshark.md) for packet-level analysis that complements Nmap's discovery scans.
- See [Networking/Connectivity.md](../Networking/Connectivity.md) for the broader diagnostic context Nmap fits into.
l