# Linux Commands

Quick reference for commonly used Linux command-line tools.

---

## Networking

| Command | Purpose |
|---|---|
| `ip a` | Shows all network interfaces and their IP addresses |
| `ip route` | Displays the routing table |
| `ping <host>` | Tests basic connectivity to a host |
| `traceroute <host>` | Shows the path packets take to a destination |
| `dig <domain>` | Queries DNS with detailed output |
| `nslookup <domain>` | Queries DNS to resolve a domain name |
| `ss -tulnp` | Shows listening ports and associated processes |
| `nmcli` | Manages NetworkManager connections from the command line |

---

## System & Processes

| Command | Purpose |
|---|---|
| `top` / `htop` | Displays real-time system resource usage and running processes |
| `ps aux` | Lists all currently running processes |
| `kill <pid>` | Terminates a process by its process ID |
| `kill -9 <pid>` | Forcefully terminates a process |
| `df -h` | Shows disk space usage in human-readable format |
| `free -h` | Shows memory (RAM) usage |
| `uname -a` | Displays system and kernel information |
| `reboot` | Restarts the system |
| `shutdown now` | Shuts down the system immediately |

---

## Services (systemd)

| Command | Purpose |
|---|---|
| `systemctl status <service>` | Shows whether a service is running |
| `systemctl start <service>` | Starts a service |
| `systemctl stop <service>` | Stops a service |
| `systemctl restart <service>` | Restarts a service |
| `systemctl enable <service>` | Sets a service to start automatically at boot |
| `journalctl -u <service>` | Shows logs for a specific service |

---

## Permissions & Users

| Command | Purpose |
|---|---|
| `chmod <perms> <file>` | Changes file/directory permissions |
| `chown <user>:<group> <file>` | Changes file/directory owner and group |
| `ls -l` | Lists files with detailed permission info |
| `whoami` | Displays the currently logged-in username |
| `sudo <command>` | Runs a command with elevated (root) privileges |
| `passwd` | Changes the current user's password |

---

## Files & Directories

| Command | Purpose |
|---|---|
| `cd <directory>` | Changes the current directory |
| `ls` | Lists files and folders |
| `cp <source> <destination>` | Copies a file |
| `mv <source> <destination>` | Moves or renames a file |
| `rm <file>` | Deletes a file |
| `cat <file>` | Displays the contents of a file |
| `grep <pattern> <file>` | Searches for text matching a pattern within a file |

---

## Related

- See [Linux/Networking.md](../Linux/Networking.md), [Linux/Permissions.md](../Linux/Permissions.md), and [Linux/Services.md](../Linux/Services.md) for context on when to use these tools.
