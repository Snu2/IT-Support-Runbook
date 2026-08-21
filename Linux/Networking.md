# Linux Networking

Reference guide covering Linux networking fundamentals, key configuration files, and common diagnostic tools.

---

## How Linux Networking Differs from Windows

Linux networking is managed through configuration files and command-line tools rather than a graphical interface (though modern desktop distros do offer GUI options). Most servers are managed entirely via the command line, so comfort with these tools is essential for Linux-based IT support.

Network management varies slightly between distributions and tools in use:
- **NetworkManager:** Common on desktop distros (Ubuntu Desktop, Fedora)
- **systemd-networkd:** Common on servers and minimal installs
- **netplan:** Used on newer Ubuntu versions to configure the above

---

## Key Networking Files & Locations

| File/Location | Purpose |
|---|---|
| `/etc/hosts` | Manual hostname-to-IP mappings (local override of DNS) |
| `/etc/resolv.conf` | DNS resolver configuration |
| `/etc/netplan/*.yaml` | Network configuration on newer Ubuntu systems |
| `/etc/network/interfaces` | Network configuration on older Debian-based systems |
| `/etc/nsswitch.conf` | Defines the order of name resolution sources |

---

## Common Networking Commands

| Command | Purpose |
|---|---|
| `ip a` | Shows all network interfaces and their IP addresses |
| `ip route` | Displays the routing table |
| `ping <host>` | Tests basic connectivity |
| `traceroute <host>` | Shows the path packets take to a destination |
| `dig <domain>` | Queries DNS, with more detail than `nslookup` |
| `netstat -tulnp` | Shows listening ports and associated processes |
| `ss -tulnp` | Modern replacement for `netstat`, faster on large systems |
| `nmcli` | Command-line tool for managing NetworkManager connections |

---

## Key Concepts

- **Interface Naming:** Modern Linux uses predictable names (e.g., `eth0`, `enp0s3`) rather than fixed generic names, based on hardware location.
- **DHCP vs. Static IP:** Configured per-interface, either via NetworkManager, netplan, or manual file editing depending on the distro.
- **Firewall (iptables/nftables/ufw):** Linux firewalls control traffic at the packet level; `ufw` (Uncomplicated Firewall) is a simplified frontend commonly used on Ubuntu.
- **SSH:** The standard way to remotely access and manage Linux systems, using port 22 by default.

---

## Common Issues

- **No network connectivity after boot:** Check `ip a` to confirm an IP was assigned; if not, investigate the DHCP client or static configuration file for that distro.
- **DNS not resolving:** Check `/etc/resolv.conf` for valid DNS server entries — this file is sometimes overwritten automatically by network management tools.
- **Cannot SSH into a server:** Verify the SSH service is running (`systemctl status ssh`), the firewall allows port 22, and the correct IP/credentials are being used.
- **Interface shows as down:** Use `ip link set <interface> up` to bring it online, or check physical/virtual connection first.

---

## Related

- See [Linux/Permissions.md](Permissions.md) for file and user permission concepts relevant to network configuration files.
- See [Commands/Linux.md](../Commands/Linux.md) for the full list of Linux command-line tools.
