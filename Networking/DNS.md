# DNS (Domain Name System)

Reference guide covering how DNS works, record types, and common DNS concepts.

---

## How DNS Works

DNS translates human-readable domain names (e.g., `google.com`) into IP addresses that computers use to identify each other on a network. Without DNS, users would need to memorize IP addresses for every website they visit.

**Basic resolution process:**
1. User types a domain name into a browser
2. The device checks its local DNS cache first
3. If not cached, it queries a **DNS resolver** (usually provided by the ISP or a public resolver like Google DNS)
4. The resolver queries **root servers**, then **TLD servers** (.com, .org, etc.), then the **authoritative name server** for that domain
5. The authoritative server returns the IP address
6. The browser connects to that IP address

This entire process typically takes milliseconds and is cached at multiple levels to speed up future requests.

---

## Common DNS Record Types

| Record Type | Purpose |
|---|---|
| A | Maps a domain to an IPv4 address |
| AAAA | Maps a domain to an IPv6 address |
| CNAME | Maps a domain to another domain (alias) |
| MX | Specifies mail servers for the domain |
| TXT | Stores text data, often used for verification or SPF/DKIM records |
| NS | Specifies the authoritative name servers for the domain |
| PTR | Used for reverse DNS lookups (IP to domain) |

---

## Key DNS Concepts

- **DNS Cache:** Temporary storage of DNS lookup results, kept locally (on a device) or by a resolver, to speed up repeat requests.
- **TTL (Time to Live):** How long a DNS record is cached before it must be looked up again.
- **Authoritative DNS Server:** The server that holds the actual DNS records for a domain and provides the official answer.
- **Recursive Resolver:** A server that performs the full lookup process on behalf of the user, querying other servers as needed.
- **DNS Propagation:** The time it takes for DNS changes to update across all servers globally (can take up to 48 hours, though usually much faster).

---

## Common DNS Issues

- **Domain not resolving:** Often caused by incorrect DNS records, expired domain registration, or propagation delays after a change.
- **Slow resolution:** Can result from an overloaded or distant DNS resolver — switching to a faster public resolver (e.g., 8.8.8.8 or 1.1.1.1) can help.
- **Stale cache:** Old cached DNS data can cause a device to connect to an outdated IP address after a change. Clearing the local DNS cache resolves this.

---

## Related

- See [Troubleshooting/DNS.md](../Troubleshooting/DNS.md) for step-by-step diagnosis of DNS-related issues.
- See [Commands/Network.md](../Commands/Network.md) for relevant command-line tools (`nslookup`, `ipconfig /flushdns`).
