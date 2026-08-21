# Windows Services

Reference guide covering what Windows services are, how they work, and common service-related troubleshooting concepts.

---

## What Are Windows Services

Services are background processes that run without requiring a user to be logged in or interacting with them. They handle core system functions like networking, printing, updates, and security — most of what Windows does behind the scenes runs as a service.

Services can be managed through the **Services** console (`services.msc`), which allows starting, stopping, restarting, and configuring how each service behaves.

---

## Service Startup Types

| Startup Type | Behavior |
|---|---|
| Automatic | Starts when Windows boots, without user interaction |
| Automatic (Delayed Start) | Starts shortly after boot, to reduce startup load |
| Manual | Only starts when needed, triggered by another process or user action |
| Disabled | Will not start under any circumstance until re-enabled |

---

## Common Critical Services

| Service | Purpose |
|---|---|
| DHCP Client | Manages network configuration via DHCP |
| DNS Client | Handles DNS resolution and caching |
| Print Spooler | Manages print jobs and printer communication |
| Windows Update | Handles downloading and installing updates |
| Windows Defender Antivirus Service | Provides real-time malware protection |
| Remote Desktop Services | Enables remote desktop connections |

---

## Key Service Concepts

- **Dependency:** Some services rely on other services to function — if a dependency is stopped, the dependent service may fail to start.
- **Service Account:** The identity a service runs under (e.g., Local System, Network Service), which determines its permissions on the machine.
- **Service Status:** Whether a service is currently Running, Stopped, or Paused — the first thing to check when a related feature isn't working.
- **Recovery Options:** Windows allows configuring what happens if a service fails (e.g., restart automatically, run a program, or take no action).

---

## Common Service Issues

- **Feature not working (e.g., printing fails):** Often traced back to the related service being stopped or crashed — check its status in `services.msc` and restart it.
- **Service won't start:** Can be caused by a missing dependency, corrupted files, or a conflicting configuration — check the Event Viewer for specific error details.
- **Service starts then stops immediately:** Usually indicates an underlying error the service encounters right after starting — Event Viewer logs are the best place to investigate.
- **High resource usage from a service:** Use Task Manager's "Services" tab to identify which service is consuming excessive CPU or memory.

---

## Related

- See [Windows/Printers.md](Printers.md) for the Print Spooler service in a real troubleshooting context.
- See [Commands/Windows.md](../Commands/Windows.md) for relevant command-line tools (`sc query`, `net start`, `net stop`).
