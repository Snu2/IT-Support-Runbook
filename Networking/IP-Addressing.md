# IP Addressing (IPv4, IPv6, and MAC Addresses)

Reference guide covering IP addressing fundamentals, the difference between IPv4 and IPv6, and how MAC addresses fit into device identification.

---

## What Is an IP Address

An IP address is a unique numerical identifier assigned to a device on a network, used to locate and communicate with it — similar to a mailing address for data. Every device that communicates on a network (local or internet) needs one.

There are two versions in use today: **IPv4** and **IPv6**.

---

## IPv4

IPv4 is the original and still most widely used addressing system. It uses a 32-bit address written as four decimal numbers separated by dots.

**Format:** `192.168.1.1`

Each of the four numbers ranges from 0–255, giving a theoretical maximum of about 4.3 billion unique addresses — a number the internet has already outgrown, which is the main reason IPv6 was introduced.

### IPv4 Address Classes (Private Ranges)

| Range | Common Use |
|---|---|
| 10.0.0.0 – 10.255.255.255 | Large private networks |
| 172.16.0.0 – 172.31.255.255 | Medium private networks |
| 192.168.0.0 – 192.168.255.255 | Small/home private networks |

Private IP addresses are used inside local networks and aren't directly reachable from the internet — devices share a single public IP via NAT (see [Networking/Routing.md](Routing.md)).

---

## IPv6

IPv6 was developed to solve IPv4's address exhaustion problem, using a 128-bit address space — enough addresses that exhaustion is not a practical concern for the foreseeable future.

**Format:** `2001:0db8:85a3:0000:0000:8a2e:0370:7334`
(often shortened by omitting leading zeros and collapsing consecutive zero groups with `::`, e.g., `2001:db8:85a3::8a2e:370:7334`)

### Key Differences from IPv4

| Aspect | IPv4 | IPv6 |
|---|---|---|
| Address length | 32-bit | 128-bit |
| Format | Decimal, dot-separated | Hexadecimal, colon-separated |
| Total addresses | ~4.3 billion | Effectively unlimited |
| NAT requirement | Common (due to address scarcity) | Generally unnecessary |
| Adoption | Universal, legacy standard | Growing, not yet universal |

Most modern networks run IPv4 and IPv6 simultaneously (called dual-stack) during this long transition period.

---

## MAC Address

A MAC (Media Access Control) address is a unique hardware identifier burned into a device's network interface — unlike an IP address, it doesn't change based on which network you connect to.

**Format:** `00:1A:2B:3C:4D:5E` (six pairs of hexadecimal digits)

### IP Address vs. MAC Address

| Aspect | IP Address | MAC Address |
|---|---|---|
| Layer | Network layer (logical) | Data link layer (physical) |
| Assigned by | DHCP or manually configured | Set by the manufacturer (hardware) |
| Changes? | Can change (different networks, DHCP renewal) | Fixed to the physical adapter (though can be spoofed) |
| Scope | Can route across networks | Only relevant on the local network segment |

Both work together: the IP address gets data to the right network, and the MAC address delivers it to the right device once it arrives on that local network segment.

---

## Key Concepts

- **Subnetting:** Dividing an IP range into smaller networks — see [Networking/Routing.md](Routing.md) for related routing concepts.
- **NAT (Network Address Translation):** Allows many devices with private IPv4 addresses to share one public IP, conserving the limited IPv4 address space.
- **MAC Address Spoofing:** Software can present a different MAC address than the hardware's actual one — sometimes used for privacy, but also a potential security bypass technique to be aware of.
- **Link-Local Address:** An IPv6 address automatically assigned for communication only within the local network segment, not routable beyond it.

---

## Finding These Addresses

| Platform | Command |
|---|---|
| Windows | `ipconfig /all` (shows IPv4, IPv6, and Physical/MAC Address) |
| Linux | `ip a` |
| macOS | `ifconfig` or `networksetup -getmacaddress` |

---

## Related

- See [Networking/DHCP.md](DHCP.md) for how IP addresses are automatically assigned.
- See [Networking/Routing.md](Routing.md) for how IP addresses are used to route traffic between networks.
- See [Commands/Windows.md](../Commands/Windows.md) and [Commands/Linux.md](../Commands/Linux.md) for the commands referenced above.
