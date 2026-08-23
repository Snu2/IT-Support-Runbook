# Network Hardware & Infrastructure

Reference guide covering the physical devices and infrastructure that make networks function — from home equipment to the towers and satellites that connect networks globally.

---

## Router

A router connects different networks together and directs traffic between them — most commonly connecting a home or office local network to the internet.

**Key functions:**
- Assigns local IP addresses to devices (often acting as the DHCP server — see [Networking/DHCP.md](DHCP.md))
- Performs NAT (Network Address Translation) so multiple devices share one public IP
- Makes routing decisions to forward traffic toward its destination (see [Networking/Routing.md](Routing.md))
- Often includes a built-in firewall to filter unwanted incoming traffic

In most homes, the "router" is actually a combo device that also includes a switch and Wi-Fi access point in one box.

---

## Switch

A switch connects multiple devices within the same local network, allowing them to communicate directly with each other.

**Key concepts:**
- Operates primarily using MAC addresses (see [Networking/IP-Addressing.md](IP-Addressing.md)) to forward data only to the intended device, rather than broadcasting to everyone
- **Unmanaged switches:** Simple, plug-and-play, no configuration — common in homes and small offices
- **Managed switches:** Configurable (VLANs, port monitoring, traffic prioritization) — common in business/enterprise environments

A switch does not connect to the internet on its own — it only handles traffic within the local network; a router is still needed to reach outside networks.

---

## Modem

A modem connects a local network to the Internet Service Provider's (ISP) infrastructure, converting signals between the format used by the ISP's connection (cable, fiber, DSL) and the format used by home/office networking equipment.

**Key point:** A modem alone does not create a local network or assign IP addresses to multiple devices — that's the router's job. Many ISP-provided devices combine both into a single "gateway" unit.

| Device | Primary Role |
|---|---|
| Modem | Connects to the ISP, translates the incoming signal |
| Router | Distributes internet access to local devices, manages local network |
| Switch | Connects multiple wired devices within the local network |

---

## Fiber Optic Cable

Fiber optic cable transmits data as pulses of light through thin strands of glass or plastic, rather than electrical signals through copper wire. It's the backbone of modern high-speed internet, both for long-distance internet infrastructure and increasingly for home connections (FTTH — Fiber to the Home).

**Why fiber is used:**

| Advantage | Explanation |
|---|---|
| Speed | Supports much higher bandwidth than copper cabling |
| Distance | Signal travels far with minimal loss, unlike copper which degrades over distance |
| Interference resistance | Immune to electromagnetic interference, unlike copper cables |
| Security | Harder to tap into without physical, detectable intrusion |

**Key concepts:**
- **Single-mode fiber:** Uses a thin core and a single light path, suited for long-distance transmission (used by ISPs, undersea cables, backbone networks).
- **Multi-mode fiber:** Uses a thicker core allowing multiple light paths, suited for shorter distances (common within data centers and buildings).
- **Undersea Cables:** The vast majority of international internet traffic travels through fiber optic cables laid across ocean floors connecting continents — not through satellites, as is commonly assumed.
- **Last Mile:** The final stretch of cabling connecting an ISP's network to an individual home or business — historically often copper, but increasingly being upgraded to fiber (FTTH) for much faster speeds.

---

## Cell Towers

Cell towers provide wireless network connectivity for mobile devices over large geographic areas, forming the backbone of mobile (cellular) networks.

**How it works:**
1. A mobile device connects to the nearest cell tower via radio signals
2. The tower connects back to the mobile carrier's core network
3. From there, traffic routes to the destination — whether another phone call, a website, or a data service — through the broader internet infrastructure

**Key concepts:**
- **Cell:** The geographic coverage area of a single tower; networks are divided into overlapping cells to provide continuous coverage as devices move
- **Handoff:** When a moving device switches from one tower's coverage to another without dropping the connection
- **Generations (3G, 4G/LTE, 5G):** Each generation offers improvements in speed, latency, and capacity — 5G in particular enables much higher speeds and supports far more connected devices per area

---

## Satellites

Satellite internet provides connectivity in areas where laying physical cables or building towers isn't practical (rural areas, ships, remote regions), by relaying signals between a ground station and an orbiting satellite.

**Types of satellite orbits used for internet:**

| Orbit Type | Altitude | Latency | Notes |
|---|---|---|---|
| GEO (Geostationary) | ~35,800 km | High (~600ms+) | Traditional satellite internet; stays fixed over one location |
| MEO (Medium Earth Orbit) | ~2,000–35,000 km | Moderate | Less common for consumer internet |
| LEO (Low Earth Orbit) | ~500–2,000 km | Low (~20–40ms) | Used by modern services like Starlink; requires many satellites working together |

**Key concept — Latency tradeoff:** GEO satellites cover huge areas with just one satellite but introduce significant delay due to the distance signals travel. LEO constellations reduce latency dramatically but require hundreds or thousands of satellites working together to maintain coverage as they orbit quickly.

---

## How It All Connects (Simplified Flow)

```
Your Device → Wi-Fi/Ethernet → Router → Modem → Fiber/Copper Line → ISP Network → Internet Backbone (mostly fiber) → Destination Server
```

For mobile devices without Wi-Fi:
```
Your Device → Cell Tower → Carrier Network → Internet Backbone → Destination Server
```

For remote/rural connectivity:
```
Your Device → Router → Satellite Dish → Orbiting Satellite → Ground Station → ISP Network → Internet
```

---

## Related

- See [Networking/Connectivity.md](Connectivity.md) for the layered troubleshooting approach these devices fit into.
- See [Networking/Routing.md](Routing.md) for how routers make forwarding decisions.
- See [Networking/DHCP.md](DHCP.md) for how routers assign addresses to local devices.
