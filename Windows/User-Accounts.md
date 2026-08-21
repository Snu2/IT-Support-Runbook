# Windows User Accounts

Reference guide covering Windows user account types, management, and common account-related concepts.

---

## User Account Types

| Account Type | Permissions | Typical Use |
|---|---|---|
| Administrator | Full control over the system, can install software, change settings | IT admins, system setup |
| Standard User | Limited permissions, cannot make system-wide changes | Everyday end users |
| Guest | Very limited, temporary access | Shared/public devices |
| Local Account | Exists only on that specific device | Standalone machines |
| Microsoft Account | Cloud-linked, syncs settings across devices | Personal devices |
| Domain Account | Managed centrally via Active Directory | Corporate/enterprise environments |

---

## Local vs. Domain Accounts

- **Local Account:** Credentials are stored only on the local machine. Useful for standalone devices, but doesn't scale well for managing many machines.
- **Domain Account:** Credentials are managed centrally by a domain controller (Active Directory). Allows IT to control permissions, apply policies, and manage password resets across an entire organization from one place.

In a business environment, most user accounts are domain accounts so administrators can enforce security policies (password complexity, lockout rules, group permissions) consistently.

---

## Key Account Concepts

- **User Profile:** The folder and settings unique to each user (desktop, documents, app settings), stored separately so multiple users can share one device.
- **User Account Control (UAC):** The prompt that appears when an action requires administrator approval — a security layer to prevent unauthorized changes.
- **Group Policy:** A Windows feature (used in domain environments) to centrally manage settings and restrictions across many user accounts and computers at once.
- **Account Lockout:** A security feature that temporarily disables an account after repeated failed login attempts, protecting against brute-force attacks.
- **Password Reset vs. Account Unlock:** Two different actions — a reset changes the password, while an unlock just clears a lockout after too many failed attempts (the password may still be correct).

---

## Common User Account Issues

- **User locked out after failed logins:** Usually resolved by an admin unlocking the account via Active Directory Users and Computers (domain) or Local Users and Groups (local machine).
- **User can't access a shared resource:** Often a permissions or group membership issue — verify the user is in the correct security group.
- **Profile fails to load ("temporary profile" error):** Can indicate a corrupted user profile; may require creating a new profile and migrating data.
- **Forgotten password with no reset option:** For local accounts without a linked recovery method, this typically requires admin intervention or, in some cases, a password reset disk/tool.

---

## Related

- See [Security/Account-Compromise.md](../Security/Account-Compromise.md) for handling suspected unauthorized account access.
- See [Commands/Windows.md](../Commands/Windows.md) for relevant command-line tools (`net user`, `whoami`).
