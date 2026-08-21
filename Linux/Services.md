# Linux Services

Reference guide covering how services work on Linux (systemd), managing them, and common service-related troubleshooting concepts.

---

## How Linux Services Work

Most modern Linux distributions use **systemd** to manage services (called "units"). Systemd handles starting services at boot, restarting them if they crash, and managing dependencies between them — similar in purpose to the Windows Services console, but managed entirely via the command line.

Services are commonly referred to as "daemons" in Linux, often named with a trailing `d` (e.g., `sshd`, `httpd`, `crond`).

---

## Core systemd Commands

| Command | Purpose |
|---|---|
| `systemctl status <service>` | Shows whether a service is running and recent log output |
| `systemctl start <service>` | Starts a service immediately |
| `systemctl stop <service>` | Stops a running service |
| `systemctl restart <service>` | Stops then starts a service |
| `systemctl enable <service>` | Configures a service to start automatically at boot |
| `systemctl disable <service>` | Prevents a service from starting at boot |
| `journalctl -u <service>` | Shows detailed logs for a specific service |

---

## Service States

| State | Meaning |
|---|---|
| active (running) | Service is currently running normally |
| inactive (dead) | Service is stopped |
| failed | Service attempted to start but crashed or errored |
| enabled | Service is set to start automatically at boot |
| disabled | Service will not start automatically at boot |

---

## Common Services

| Service | Purpose |
|---|---|
| `sshd` | Enables remote SSH access to the system |
| `cron` / `crond` | Runs scheduled tasks |
| `networking` / `NetworkManager` | Manages network connections |
| `firewalld` / `ufw` | Manages firewall rules |
| `nginx` / `apache2` | Common web server services |

---

## Key Concepts

- **Unit File:** The configuration file (usually in `/etc/systemd/system/` or `/lib/systemd/system/`) that defines how a service behaves — what it runs, its dependencies, and restart policy.
- **Dependency:** Like Windows services, a systemd service can depend on others being active first; a failed dependency often causes a cascading failure.
- **Logs via journalctl:** Unlike Windows Event Viewer, systemd centralizes logs through `journalctl`, making it the primary tool for diagnosing why a service failed.
- **Masking a Service:** A stronger form of disabling that prevents a service from being started even manually or by another service — used to fully block a problematic service.

---

## Common Service Issues

- **Service fails to start:** Run `systemctl status <service>` first for a quick error summary, then `journalctl -u <service>` for full logs.
- **Service works but doesn't survive reboot:** Usually means it was started manually but never `enabled` — run `systemctl enable <service>`.
- **Port already in use error:** Another process is likely already using that port — check with `ss -tulnp` to identify it.
- **Service in "failed" state after a crash:** Check logs first, then attempt `systemctl restart`; repeated failures often point to a configuration error in the unit file or application itself.

---

## Related

- See [Linux/Networking.md](Networking.md) for network-related services like `sshd` and `NetworkManager`.
- See [Commands/Linux.md](../Commands/Linux.md) for the full list of Linux command-line tools.
