# Troubleshooting: DNS Issues

Step-by-step diagnosis and resolution for DNS resolution problems.

> See [Networking/DNS.md](../Networking/DNS.md) for background on how DNS works.

---

## Symptom: Cannot Access a Specific Website or Service

**Possible causes:** Incorrect DNS records, expired domain, stale cache, blocked by firewall/proxy, DNS server issue.

### Diagnosis Steps

1. **Try accessing the site from a different device/network** to isolate whether the issue is device-specific or network-wide.
2. **Run `nslookup <domain>`** to check whether DNS resolution succeeds and what IP it returns.
3. **Clear the local DNS cache** — `ipconfig /flushdns` (Windows) or equivalent on other OSes — to rule out stale cached data.
4. **Check if a firewall or proxy is blocking the site** rather than a DNS issue itself (the site may resolve fine but still fail to load).
5. **Test using a different DNS server** (e.g., 8.8.8.8 or 1.1.1.1) to determine if the issue is with the current DNS resolver specifically.

### Resolution

- If DNS resolution fails entirely, update DNS server settings to a known-working resolver.
- If resolution succeeds but the site still doesn't load, the issue is likely firewall/proxy or the destination server itself — not DNS.
- If only one device is affected, check that device's `hosts` file for incorrect manual entries overriding DNS.

---

## Symptom: All Domains Fail to Resolve

**Possible causes:** No DNS server configured, DNS server unreachable, broader connectivity issue.

### Diagnosis Steps

1. Confirm basic connectivity first (see [Networking/Connectivity.md](../Networking/Connectivity.md)) — if there's no internet access at all, DNS won't work either.
2. Check the device's configured DNS servers (`ipconfig /all` on Windows, `/etc/resolv.conf` on Linux).
3. Try pinging the configured DNS server's IP directly to check if it's reachable.

### Resolution

- If DNS servers aren't configured, this typically points back to a DHCP issue (see [Networking/DHCP.md](../Networking/DHCP.md)).
- If the configured DNS server is unreachable, switch to a public DNS resolver temporarily to confirm this is the cause.

---

## Related

- [Networking/DNS.md](../Networking/DNS.md) — DNS fundamentals and record types
- [Networking/Connectivity.md](../Networking/Connectivity.md) — layered connectivity troubleshooting
- [Commands/Network.md](../Commands/Network.md) — Diagnostic commands referenced above
