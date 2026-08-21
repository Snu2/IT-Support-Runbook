# Endpoint Security

Reference guide covering endpoint security fundamentals, common protections, and key concepts for securing individual devices.

---

## What Is Endpoint Security

An "endpoint" is any device that connects to a network — laptops, desktops, phones, servers, and even IoT devices. Endpoint security focuses on protecting these individual devices, since each one represents a potential entry point for an attacker.

As organizations increasingly support remote work and personal devices, endpoints have become one of the most common targets for attacks — making endpoint protection a core part of IT support.

---

## Core Endpoint Protections

| Protection | Purpose |
|---|---|
| Antivirus / Anti-malware | Detects and removes known malicious software |
| EDR (Endpoint Detection & Response) | Monitors endpoint behavior in real time to detect and respond to threats, including unknown ones |
| Firewall | Controls inbound/outbound network traffic on the device |
| Disk Encryption | Protects data if a device is lost or stolen (e.g., BitLocker, FileVault) |
| Patch Management | Ensures OS and software stay updated against known vulnerabilities |
| MDM (Mobile Device Management) | Allows centralized management and enforcement of security policies across devices |

---

## Key Concepts

- **Antivirus vs. EDR:** Traditional antivirus relies on known malware signatures, while EDR monitors behavior patterns — allowing it to catch novel or previously unseen threats that antivirus alone would miss.
- **Zero-Day Vulnerability:** A security flaw that is unknown to the vendor (and therefore unpatched), making it especially dangerous until a fix is released.
- **Patch Management:** The process of keeping software updated to close known security gaps — one of the single most effective ways to prevent breaches.
- **Least Privilege:** Giving users and applications only the access they need to do their job, reducing the potential damage if an account or device is compromised.
- **Device Compliance:** In managed environments, a device must meet certain security requirements (updated OS, encryption enabled, antivirus active) before being allowed full network access.

---

## Common Endpoint Security Tasks

- **Verifying antivirus/EDR is active:** Check the relevant console (Windows Security, or a third-party EDR dashboard) to confirm real-time protection is running and definitions are up to date.
- **Confirming disk encryption status:** On Windows, check BitLocker status via `manage-bde -status` or Settings; ensures data is protected if the device is lost.
- **Applying security patches:** Regularly reviewing and applying OS and application updates, prioritizing critical security patches.
- **Isolating a compromised device:** Disconnecting a suspected infected device from the network immediately to prevent lateral spread, before further investigation.

---

## Related

- See [Security/Malware.md](Malware.md) for identifying and responding to active infections.
- See [Security/Account-Compromise.md](Account-Compromise.md) for handling compromised credentials on an endpoint.
