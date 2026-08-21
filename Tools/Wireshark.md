# Wireshark

Reference guide covering what Wireshark is, how it's used, and key concepts for network packet analysis.

---

## What Is Wireshark

Wireshark is a free, open-source network protocol analyzer that captures and displays network traffic in real time. It allows IT professionals to see exactly what data is moving across a network at the packet level — essential for diagnosing issues that basic tools like `ping` or `tracert` can't fully explain.

It's widely used for network troubleshooting, security analysis, protocol development, and education.

---

## Core Concepts

- **Packet Capture:** Wireshark captures raw data packets traveling through a selected network interface, showing their full contents and metadata.
- **Interface Selection:** Before capturing, you choose which network interface to monitor (Wi-Fi, Ethernet, VPN adapter, etc.) — traffic only appears for the interface being captured.
- **Promiscuous Mode:** Allows an interface to capture all traffic on the network segment, not just traffic addressed to that specific device (useful on hubs/mirrored switch ports; limited effect on modern switched networks).
- **Protocol Dissection:** Wireshark automatically decodes packets according to their protocol (TCP, HTTP, DNS, etc.), displaying the structured layers instead of raw binary data.

---

## The Wireshark Interface

| Panel | Purpose |
|---|---|
| Packet List | Chronological list of captured packets with summary info (source, destination, protocol) |
| Packet Details | Expandable breakdown of the selected packet's protocol layers |
| Packet Bytes | Raw hex/ASCII view of the selected packet's actual data |
| Display Filter Bar | Where filters are typed to narrow down which packets are shown |

---

## Common Display Filters

| Filter | Purpose |
|---|---|
| `ip.addr == 192.168.1.1` | Show only traffic to/from a specific IP |
| `tcp.port == 443` | Show only traffic on a specific port |
| `http` | Show only HTTP traffic |
| `dns` | Show only DNS queries and responses |
| `tcp.flags.syn == 1` | Show only TCP connection attempts (SYN packets) |
| `frame contains "error"` | Show packets containing specific text |

Filters can be combined using `&&` (and), `||` (or), and `!` (not) — e.g., `ip.addr == 192.168.1.1 && tcp.port == 443`.

---

## Common Use Cases

- **Diagnosing slow network performance:** Capturing traffic to spot retransmissions, delays, or unexpected chatty protocols consuming bandwidth.
- **Investigating failed connections:** Watching the TCP handshake (SYN, SYN-ACK, ACK) to see exactly where a connection attempt fails.
- **Verifying DNS resolution:** Confirming what DNS queries a device is actually sending and what responses it receives.
- **Security analysis:** Spotting suspicious traffic patterns, unencrypted credential transmission, or unexpected outbound connections (see [Security/Malware.md](../Security/Malware.md) for related concepts like C2 traffic).

---

## Best Practices

- Capture only what's needed — use filters or a capture time limit to avoid overwhelming, hard-to-analyze files.
- Be mindful of privacy and authorization — only capture traffic on networks/devices you have explicit permission to monitor.
- Save captures as `.pcap`/`.pcapng` files for later analysis or sharing with a team.

---

## Related

- See [Networking/Connectivity.md](../Networking/Connectivity.md) for the layered approach Wireshark helps investigate.
- See [Tools/Nmap.md](Nmap.md) for network discovery, which pairs well with packet-level analysis.
