# Routing

Reference guide covering how network routing works, routing tables, and common routing concepts.

---

## How Routing Works

Routing is the process of directing data packets between different networks so they reach their intended destination. Every device on a network relies on routing to communicate with anything outside its local network segment.

**Basic flow:**
1. A device wants to send data to an IP address outside its local network
2. It checks its routing table to determine where to send the packet next
3. If no specific route matches, it sends the packet to its **default gateway** (usually a router)
4. The router examines the destination and forwards the packet toward the next hop
5. This continues, hop by hop, until the packet reaches its destination network

Each device that forwards the packet along the way is called a "hop" — this is what tools like `tracert`/`traceroute` reveal.

---

## Routing Table Basics

A routing table tells a device or router where to send traffic based on destination. Key fields include:

| Field | Purpose |
|---|---|
| Destination | The target network or IP range |
| Subnet Mask | Defines the size of the destination network |
| Gateway | The next-hop address packets are sent to |
| Interface | Which network interface the traffic goes out through |
| Metric | A cost value used to choose between multiple possible routes (lower is preferred) |

---

## Static vs. Dynamic Routing

| Type | Description | Use Case |
|---|---|---|
| Static Routing | Routes manually configured by an admin | Small, simple, or stable networks |
| Dynamic Routing | Routes automatically learned and updated using routing protocols (e.g., OSPF, BGP, RIP) | Larger, complex, or frequently changing networks |

Dynamic routing adapts automatically to network changes (like a link going down), while static routing requires manual updates but offers more predictable, controlled behavior.

---

## Key Routing Concepts

- **Default Gateway:** The device (usually a router) that traffic is sent to when no more specific route is known — effectively the "exit point" of a local network.
- **Hop:** Each intermediate device (usually a router) that a packet passes through on its way to its destination.
- **Latency:** The time delay introduced as data travels across the network, often increasing with each additional hop.
- **NAT (Network Address Translation):** Allows multiple devices on a private network to share a single public IP address when routing traffic to the internet.
- **Subnetting:** Dividing a network into smaller segments, which affects how routing decisions are made between them.

---

## Common Routing Issues

- **Cannot reach specific networks/sites while others work fine:** May indicate a missing or incorrect route, or an issue at a specific hop — use `tracert`/`traceroute` to pinpoint where traffic stops.
- **High latency:** Often caused by too many hops, network congestion, or a poorly performing link somewhere along the path.
- **Routing loops:** Misconfigured routes can cause packets to circulate endlessly between routers instead of reaching their destination, typically seen as connection timeouts.

---

## Related

- See [Troubleshooting/Slow-Network.md](../Troubleshooting/Slow-Network.md) for diagnosing performance issues related to routing.
- See [Commands/Network.md](../Commands/Network.md) for relevant command-line tools (`tracert`, `traceroute`, `netstat -r`).
