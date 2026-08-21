# Connectivity

Reference guide covering network connectivity fundamentals, how connections are established, and common concepts used to diagnose connectivity issues.

---

## What "Connectivity" Means

Connectivity refers to a device's ability to successfully communicate with other devices, networks, or the internet. A connectivity issue can occur at any layer — from a physical cable, to Wi-Fi signal, to DNS, to the destination server itself — so diagnosing it usually means checking each layer in order.

---

## The Layered View of Connectivity

A useful way to think about connectivity problems is to check them in order, from closest to the device to furthest away:

| Layer | What to Check | Example Tool |
|---|---|---|
| Physical | Cable connected, Wi-Fi adapter enabled | Visual check, Device Manager |
| Local Network | Device has a valid IP address | `ipconfig` / `ifconfig` |
| Gateway | Device can reach its router | `ping <gateway IP>` |
| DNS | Domain names resolve to IP addresses | `nslookup` |
| Internet | Device can reach external hosts | `ping 8.8.8.8` |
| Application | The specific service/site is reachable | Browser, `telnet`, port checks |

Working through this order quickly narrows down where a connectivity problem actually lives.

---

## Key Connectivity Concepts

- **Link Status:** Whether a physical or wireless connection is active at all — the most basic check before anything else.
- **Ping:** Sends a small packet to a destination and measures whether (and how fast) it responds — the fastest way to confirm basic reachability.
- **Packet Loss:** When some data sent across a network doesn't arrive, often causing lag, dropped calls, or failed page loads.
- **Latency:** The time it takes for data to travel from source to destination, measured in milliseconds.
- **Bandwidth vs. Throughput:** Bandwidth is the maximum possible data rate of a connection; throughput is the actual data rate achieved, which is often lower due to congestion or overhead.

---

## Common Connectivity Issues

- **No connectivity at all:** Start at the physical layer — check cables, Wi-Fi toggle, or airplane mode before assuming a deeper issue.
- **Connected but "no internet":** Usually means the device has a local IP but can't reach the gateway or beyond — check the default gateway and DNS settings.
- **Intermittent connectivity:** Often caused by weak Wi-Fi signal, interference, or an unstable ISP connection — worth testing with a wired connection to isolate the cause.
- **Works on one device but not another:** Points to a device-specific issue (drivers, settings, firewall) rather than a network-wide problem.

---

## Related

- See [Troubleshooting/WiFi.md](../Troubleshooting/WiFi.md) and [Troubleshooting/VPN.md](../Troubleshooting/VPN.md) for step-by-step diagnosis of specific connectivity scenarios.
- See [Commands/Network.md](../Commands/Network.md) for the full list of diagnostic commands referenced above.
