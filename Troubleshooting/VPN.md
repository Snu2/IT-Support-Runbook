# Troubleshooting: VPN Connection Issues

Step-by-step diagnosis and resolution for VPN connectivity problems.

---

## Symptom: VPN Fails to Connect

**Possible causes:** Incorrect credentials, wrong server address, client misconfiguration, blocked ports, expired certificate.

### Diagnosis Steps

1. **Verify credentials and VPN server address** are correct and haven't changed.
2. **Check internet connectivity without VPN first** — if the base connection is down, the VPN can't work regardless of its own configuration.
3. **Restart the VPN client** — clears temporary connection state issues.
4. **Check for conflicting network adapters or firewall rules** that may be blocking the VPN's connection attempt.
5. **Review VPN logs for specific error codes** — most VPN clients log a specific failure reason (auth failure, timeout, certificate error) that narrows the cause significantly.

### Resolution

- If credentials are the issue, reset the password or re-authenticate.
- If a firewall is blocking the connection, confirm the required VPN ports (varies by protocol — e.g., UDP 500/4500 for IPsec, TCP 443 for SSL VPN) are open.
- Reinstall the VPN client if it appears corrupted or won't update.
- If the issue is server-side (confirmed via logs/error codes), escalate to the VPN provider or network admin.

---

## Symptom: VPN Connects but Disconnects Randomly

**Possible causes:** Unstable internet connection, power-saving settings, session timeout configuration, MTU mismatch.

### Diagnosis Steps

1. Check the base internet connection's stability (see [Troubleshooting/Slow-Network.md](Slow-Network.md)) — an unstable connection will cause the VPN tunnel to drop.
2. Disable Wi-Fi adapter or network adapter power-saving settings, which can interrupt persistent connections.
3. Check the VPN client's configured session timeout or idle disconnect settings.

### Resolution

- Switch to a wired connection to test if Wi-Fi instability is the cause.
- Adjust MTU settings if packet fragmentation is suspected (common symptom: works fine for basic browsing but fails on larger transfers).

---

## Symptom: VPN Connected but No Internet Access

**Possible causes:** Split tunneling misconfiguration, DNS not routing through VPN, "kill switch" feature blocking traffic.

### Diagnosis Steps

1. Check whether split tunneling is enabled/disabled as expected for the intended use case.
2. Run `nslookup` to check if DNS is resolving through the VPN's intended DNS servers (see [Networking/DNS.md](../Networking/DNS.md)).
3. Check if the VPN client has a "kill switch" feature active that's blocking traffic due to a detected instability.

### Resolution

- Adjust split tunneling settings based on whether all traffic or only specific traffic should route through the VPN.
- Manually set DNS servers if the VPN isn't providing valid ones.

---

## Related

- [Networking/Connectivity.md](../Networking/Connectivity.md) — general connectivity troubleshooting layers
- [Networking/DNS.md](../Networking/DNS.md) — DNS resolution issues
- [Commands/Network.md](../Commands/Network.md) — Diagnostic commands referenced above
