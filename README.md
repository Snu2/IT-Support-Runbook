# IT Support Runbook

A practical, self-built knowledge base documenting IT support and networking concepts, troubleshooting procedures, diagnostic tools, and command references — organized the way real support teams structure their internal documentation.

This project was created as a hands-on learning exercise to deepen and demonstrate practical knowledge across networking, Windows, Linux, security, and diagnostic tooling.

---

## Purpose

This runbook serves two goals:
1. **A personal reference** for continuous learning and quick lookup while studying IT support and networking.
2. **A demonstration of practical, organized technical knowledge** — built and maintained entirely through Git and GitHub.

---

## Structure

```
IT-Support-Runbook/
├── IT-Support-Methodology.md   How enterprise IT support actually operates
├── Networking/                 Core networking concepts
├── Windows/                    Windows administration topics
├── Linux/                      Linux administration topics
├── Security/                   Security fundamentals and incident response
├── Troubleshooting/            Step-by-step diagnostic playbooks
├── Commands/                   Quick command-line references
└── Tools/                      Diagnostic and analysis tools
```

---

## Troubleshooting Methodology

This runbook isn't just a list of commands — every issue in [Troubleshooting/](Troubleshooting/) follows a consistent diagnostic process: identify the problem, gather information from both the user and the system, form a theory of probable cause, test that theory before acting, implement the fix, verify it actually worked, and document the outcome.

The full methodology — including how this applies in real support environments (ticketing, SLAs, support tiers) — is documented in [IT-Support-Methodology.md](IT-Support-Methodology.md).

---

## Networking

Fundamentals of how networks operate.

| File | Covers |
|---|---|
| [WiFi.md](Networking/WiFi.md) | Wi-Fi standards, security protocols, key concepts |
| [DNS.md](Networking/DNS.md) | How DNS resolution works, record types |
| [DHCP.md](Networking/DHCP.md) | The DORA lease process, scopes, reservations |
| [Routing.md](Networking/Routing.md) | Routing tables, static vs. dynamic routing |
| [Connectivity.md](Networking/Connectivity.md) | Layered approach to diagnosing connectivity |
| [IP-Addressing.md](Networking/IP-Addressing.md) | IPv4 vs. IPv6, MAC addresses, private ranges |
| [Network-Hardware.md](Networking/Network-Hardware.md) | Routers, switches, modems, fiber, cell towers, satellites |

---

## Windows

Windows administration and support topics.

| File | Covers |
|---|---|
| [User-Accounts.md](Windows/User-Accounts.md) | Account types, local vs. domain, lockouts |
| [Services.md](Windows/Services.md) | How Windows services work, startup types |
| [Printers.md](Windows/Printers.md) | Print Spooler, drivers, common print issues |
| [Performance.md](Windows/Performance.md) | CPU/memory/disk bottlenecks, diagnostic tools |

---

## Linux

Linux administration and support topics.

| File | Covers |
|---|---|
| [Networking.md](Linux/Networking.md) | Linux network config files and tools |
| [Permissions.md](Linux/Permissions.md) | File permissions, ownership, chmod/chown |
| [Services.md](Linux/Services.md) | systemd services, unit files, journalctl |

---

## Security

Security fundamentals and incident response basics.

| File | Covers |
|---|---|
| [Endpoint.md](Security/Endpoint.md) | Endpoint protection tools and concepts |
| [Phishing.md](Security/Phishing.md) | Phishing types, red flags, response steps |
| [Malware.md](Security/Malware.md) | Malware types, infection signs, response |
| [Account-Compromise.md](Security/Account-Compromise.md) | Detecting and responding to compromised accounts |

---

## Troubleshooting

Step-by-step diagnostic playbooks for common real-world issues.

| File | Covers |
|---|---|
| [WiFi.md](Troubleshooting/WiFi.md) | Diagnosing Wi-Fi connection failures/drops |
| [VPN.md](Troubleshooting/VPN.md) | Diagnosing VPN connection issues |
| [DNS.md](Troubleshooting/DNS.md) | Diagnosing DNS resolution failures |
| [Slow-Network.md](Troubleshooting/Slow-Network.md) | Diagnosing slow network performance |

---

## Commands

Quick command-line references by platform.

| File | Covers |
|---|---|
| [Windows.md](Commands/Windows.md) | Windows CMD/PowerShell commands |
| [Linux.md](Commands/Linux.md) | Linux shell commands |
| [Network.md](Commands/Network.md) | Cross-platform networking commands with a diagnostic workflow |

---

## Tools

Diagnostic and analysis tools used in real-world IT and network troubleshooting.

| File | Covers |
|---|---|
| [Wireshark.md](Tools/Wireshark.md) | Packet capture, display filters, traffic analysis |
| [Nmap.md](Tools/Nmap.md) | Network scanning, port discovery, service detection |

---

## Screenshots

Practical, hands-on screenshots are being added as they're captured, organized inside the relevant section's folder (e.g., `Networking/`). The first example — basic network diagnostics run on a Linux lab environment — is documented in [Commands/Network.md](Commands/Network.md#practical-example-linux).

---

## About This Project

This runbook is continuously updated as new topics are learned and documented. It's structured so that:
- **Reference files** (Networking, Windows, Linux, Security) explain how things work
- **Troubleshooting files** link back to reference files and focus purely on diagnosis and resolution steps
- **Command files** serve as a fast lookup without needing to search through longer explanations
- **Tools files** cover real diagnostic software used alongside built-in commands
- **IT-Support-Methodology.md** connects all of the above to how support actually operates in a real organization

Built entirely from a mobile device using the GitHub app, as part of a self-driven learning process into IT support and networking.
