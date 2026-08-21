# Linux Permissions

Reference guide covering how Linux file permissions and ownership work, and common permission-related concepts.

---

## How Linux Permissions Work

Every file and directory in Linux has an **owner**, a **group**, and a set of **permissions** that control who can read, write, or execute it. This is fundamentally different from Windows, which uses a more complex ACL (Access Control List) system by default.

Running `ls -l` shows permissions in this format:

```
-rwxr-xr-- 1 user group 4096 Jan 1 12:00 filename
```

Breaking this down:
- First character: file type (`-` = file, `d` = directory, `l` = symbolic link)
- Next 9 characters: three sets of three (Owner, Group, Others), each showing **r**ead, **w**rite, e**x**ecute

---

## Permission Types

| Symbol | Permission | Effect on Files | Effect on Directories |
|---|---|---|---|
| r | Read | View file contents | List directory contents |
| w | Write | Modify file contents | Create/delete files inside |
| x | Execute | Run the file as a program/script | Enter (`cd` into) the directory |

---

## Permission Groups

| Group | Description |
|---|---|
| Owner (u) | The user who owns the file |
| Group (g) | Users belonging to the file's assigned group |
| Others (o) | Everyone else on the system |

---

## Numeric (Octal) Permissions

Permissions can also be represented as numbers, commonly used with `chmod`:

| Number | Permission | Symbol |
|---|---|---|
| 4 | Read | r |
| 2 | Write | w |
| 1 | Execute | x |
| 0 | None | - |

Values are added together per group. For example, `755` means:
- Owner: 7 (4+2+1) = read, write, execute
- Group: 5 (4+1) = read, execute
- Others: 5 (4+1) = read, execute

---

## Key Commands

| Command | Purpose |
|---|---|
| `chmod` | Changes file/directory permissions |
| `chown` | Changes file/directory owner |
| `chgrp` | Changes the group associated with a file |
| `ls -l` | Lists files with detailed permission info |
| `sudo` | Temporarily grants elevated (root) permissions for a single command |

---

## Key Concepts

- **Root User:** The Linux superuser with unrestricted access to the entire system — most day-to-day work should avoid running as root directly.
- **sudo:** Allows a permitted user to run specific commands with elevated privileges without fully switching to the root account, improving security and accountability.
- **Sticky Bit:** A special permission (often seen on `/tmp`) that prevents users from deleting files they don't own, even if they have write access to the directory.
- **SUID/SGID:** Special permissions that let a program run with the file owner's or group's privileges rather than the user executing it — powerful, but a common target for privilege escalation if misconfigured.

---

## Common Permission Issues

- **"Permission denied" running a script:** Often means the execute bit isn't set — resolved with `chmod +x filename`.
- **Cannot edit a file despite being the owner:** Check if the file is actually owned by another user/group, or if the filesystem is mounted read-only.
- **Application fails after permission changes:** Overly broad `chmod -R 777` fixes are a common (bad) shortcut — often causes security issues and unexpected application behavior.

---

## Related

- See [Linux/Networking.md](Networking.md) for permission considerations on network configuration files.
- See [Commands/Linux.md](../Commands/Linux.md) for the full list of Linux command-line tools.
