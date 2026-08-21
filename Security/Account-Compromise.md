# Account Compromise

Reference guide covering how account compromises happen, warning signs, and response procedures.

---

## What Is an Account Compromise

An account compromise occurs when someone other than the legitimate owner gains unauthorized access to a user account — through stolen credentials, phishing, weak passwords, or reused passwords exposed in a separate data breach.

Compromised accounts are especially dangerous because attackers can use legitimate access to move through systems undetected, unlike malware which security tools may flag more easily.

---

## Common Causes

| Cause | Description |
|---|---|
| Phishing | User tricked into entering credentials on a fake login page |
| Credential Stuffing | Attacker uses leaked username/password pairs from other breaches, betting on password reuse |
| Brute Force | Automated repeated login attempts to guess a weak password |
| Malware/Keyloggers | Credentials captured directly from an infected device |
| Social Engineering | Attacker manipulates a person (e.g., posing as IT support) into revealing credentials |

---

## Warning Signs of a Compromised Account

- Login attempts or successful logins from unfamiliar locations or devices
- Password reset emails the user didn't request
- Sent emails or messages the user doesn't recognize
- Unexpected changes to account settings (forwarding rules, recovery email/phone)
- Multi-factor authentication (MFA) prompts the user didn't initiate
- Unusual account activity outside normal working hours

---

## Key Concepts

- **MFA (Multi-Factor Authentication):** Requires a second verification step beyond the password (e.g., a code, app approval, or hardware key) — one of the most effective defenses against compromised credentials.
- **Credential Reuse:** Using the same password across multiple sites — if one site is breached, all accounts using that password become vulnerable.
- **Session Hijacking:** An attacker steals an active login session (via a stolen token/cookie) rather than the password itself, bypassing the need to log in at all.
- **Impossible Travel:** A security detection pattern that flags logins from geographically distant locations occurring too close together in time to be physically possible.
- **Privilege Escalation:** Once an attacker compromises one account, they may attempt to gain access to higher-privilege accounts or systems from there.

---

## Response Procedure

1. **Disable or lock the account immediately** to stop further unauthorized access
2. **Force a password reset** — do not simply ask the user to change it themselves if compromise is confirmed, since the attacker may still have session access
3. **Revoke active sessions/tokens** so any existing unauthorized login is immediately cut off
4. **Review account activity** — check login history, sent items, forwarding rules, and recent changes for signs of what the attacker did
5. **Check for lateral movement** — determine if the compromised account was used to access other systems, files, or accounts
6. **Enable/verify MFA** on the account before restoring access
7. **Notify the user and relevant teams** per organizational incident response policy
8. **Document the incident** — cause, timeline, and remediation steps taken

---

## Related

- See [Security/Phishing.md](Phishing.md) for one of the most common ways credentials are stolen.
- See [Windows/User-Accounts.md](../Windows/User-Accounts.md) for account lockout and reset procedures.
