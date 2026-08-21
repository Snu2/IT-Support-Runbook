# Phishing

Reference guide covering what phishing is, common attack patterns, and how to recognize and respond to phishing attempts.

---

## What Is Phishing

Phishing is a social engineering attack where an attacker impersonates a trusted source (a person, company, or system) to trick someone into revealing sensitive information, clicking a malicious link, or downloading malware. It remains one of the most common entry points for security breaches, because it targets people rather than technical defenses.

---

## Common Types of Phishing

| Type | Description |
|---|---|
| Email Phishing | Mass emails impersonating a trusted brand or service, often with urgent calls to action |
| Spear Phishing | Highly targeted phishing aimed at a specific individual, using personal details to appear legitimate |
| Whaling | Spear phishing targeted specifically at executives or high-level decision-makers |
| Smishing | Phishing conducted via SMS/text message |
| Vishing | Phishing conducted via phone calls, often impersonating IT support or a bank |
| Business Email Compromise (BEC) | Attacker impersonates an executive or vendor to trick an employee into a fraudulent payment or data transfer |

---

## Common Red Flags

- **Urgency or pressure:** Messages demanding immediate action ("your account will be suspended") to prevent careful thinking.
- **Mismatched sender address:** The display name looks legitimate, but the actual email address doesn't match the claimed organization.
- **Suspicious links:** Hovering over a link reveals a URL that doesn't match the claimed destination.
- **Unexpected attachments:** Especially `.exe`, `.zip`, or macro-enabled Office files from unknown or unexpected senders.
- **Generic greetings:** "Dear Customer" instead of a real name can indicate a mass phishing attempt (though targeted attacks often personalize this).
- **Requests for credentials or sensitive info:** Legitimate organizations rarely ask for passwords or full payment details via email.

---

## Key Concepts

- **Spoofing:** Faking the sender information (email address, caller ID) to appear as a trusted source.
- **Credential Harvesting:** A common phishing goal — tricking a user into entering their username/password on a fake login page that captures the data.
- **Email Authentication (SPF, DKIM, DMARC):** DNS-based mechanisms that help verify an email actually came from the domain it claims to, reducing successful spoofing.
- **Security Awareness Training:** Ongoing user education is one of the most effective defenses against phishing, since technical filters can't catch every attempt.

---

## How to Respond to a Suspected Phishing Attempt

1. **Do not click links or open attachments** in the suspicious message
2. **Verify independently** — contact the supposed sender through a separate, known-good channel (not by replying to the suspicious message)
3. **Report it** — most organizations have a "Report Phishing" button or a designated email/security team to notify
4. **If credentials were entered:** Change the affected password immediately and check for unauthorized account activity
5. **If a link was clicked or attachment opened:** Disconnect the device from the network and escalate to the security team for investigation

---

## Related

- See [Security/Account-Compromise.md](Account-Compromise.md) for next steps if credentials were actually compromised.
- See [Security/Malware.md](Malware.md) for handling a device that may have been infected via a phishing link/attachment.
