# Troubleshooting: Slow Network Performance

Step-by-step diagnosis and resolution for slow network speed and performance issues.

---

## Symptom: Slow Browsing, Downloads, or File Transfers

**Possible causes:** Bandwidth saturation, high latency, Wi-Fi interference, ISP issues, routing problems, background applications.

### Diagnosis Steps

1. **Run `ping`** to test basic connectivity and measure latency to a reliable host (e.g., 8.8.8.8).
2. **Run `tracert`/`traceroute`** to identify where along the path delays are occurring — a spike at one specific hop points to a problem there rather than the whole path.
3. **Check bandwidth usage** — determine if multiple devices/users are saturating the connection simultaneously.
4. **Test with a wired connection** to rule out Wi-Fi as the source of slowness (see [Networking/WiFi.md](../Networking/WiFi.md) for signal/interference factors).
5. **Check for background applications** consuming bandwidth (cloud sync, auto-updates, streaming).

### Resolution

- If a specific hop shows high latency consistently, the issue may be with the ISP or an upstream network — not something fixable locally.
- If Wi-Fi is confirmed as the cause, refer to [Troubleshooting/WiFi.md](WiFi.md) for signal and interference troubleshooting.
- If bandwidth saturation is the cause, consider QoS (Quality of Service) configuration to prioritize critical traffic.
- Close or limit background applications consuming bandwidth.

---

## Symptom: Slow Performance on Specific Sites/Services Only

**Possible causes:** DNS resolution delay, server-side issue, CDN/geographic routing problem — not a general network issue.

### Diagnosis Steps

1. Confirm other sites/services perform normally — if yes, the issue is likely specific to that destination, not the local network.
2. Check DNS resolution time for that specific domain (see [Networking/DNS.md](../Networking/DNS.md)).
3. Check if the issue is reported by others (status pages, forums) — may indicate a server-side outage or degradation.

### Resolution

- If isolated to one service, there's often little to troubleshoot locally — the issue lies with that provider.
- If DNS resolution itself is slow, consider switching to a faster public DNS resolver.

---

## Key Diagnostic Reference

| Symptom Pattern | Likely Area to Investigate |
|---|---|
| Slow everywhere, wired and wireless | ISP or router issue |
| Slow only on Wi-Fi | Signal/interference (see WiFi troubleshooting) |
| Slow only on one site/service | That destination, not the local network |
| High latency at a specific traceroute hop | Issue at that point in the path, likely upstream |
| Slow only during certain hours | Bandwidth saturation from usage patterns |

---

## Related

- [Networking/Routing.md](../Networking/Routing.md) — understanding hops and latency
- [Networking/WiFi.md](../Networking/WiFi.md) — Wi-Fi specific performance factors
- [Commands/Network.md](../Commands/Network.md) — Diagnostic commands referenced above
