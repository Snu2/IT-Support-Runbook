# IT Support Methodology

Reference guide covering how IT support operates in enterprise environments — ticketing systems, support tiers, SLAs, and the professional troubleshooting process used in real organizations.

---

## Ticketing Systems

Enterprise IT support runs on ticketing systems (e.g., ServiceNow, Zendesk, Jira Service Management) rather than informal requests. Every issue is logged, tracked, and documented from start to resolution.

**A typical ticket includes:**
- Reporter's name/contact info
- Description of the issue
- Category (hardware, software, network, account, etc.)
- Priority level
- Assigned technician/team
- Status (Open, In Progress, On Hold, Resolved, Closed)
- Resolution notes

Proper documentation matters — a well-written ticket helps the next technician (or the same one, months later) understand what happened and how it was fixed.

---

## Support Tiers

Most organizations structure support in tiers, escalating issues to more specialized staff as needed.

| Tier | Role | Example Issues |
|---|---|---|
| Tier 1 | First point of contact; handles common, well-documented issues | Password resets, basic connectivity, software installation |
| Tier 2 | Deeper technical troubleshooting | Network configuration issues, application errors, hardware diagnostics |
| Tier 3 | Specialized engineers/architects | Infrastructure failures, complex security incidents, system-level bugs |

A Tier 1 technician's job isn't to solve everything — it's to resolve what they can quickly and **escalate effectively** (with clear documentation) when an issue exceeds their scope.

---

## SLAs (Service Level Agreements)

An SLA defines the expected response and resolution time for issues, usually based on priority level. Meeting SLAs is a core performance metric in support teams.

| Priority | Example Definition | Example Response Time |
|---|---|---|
| Critical (P1) | Major outage, many users affected, business-critical system down | 15–30 minutes |
| High (P2) | Significant issue affecting one user/team's ability to work | 1–4 hours |
| Medium (P3) | Issue with a workaround available, moderate impact | 1 business day |
| Low (P4) | Minor issue, cosmetic, or general request | 2–3 business days |

Correctly assessing priority — not just technical difficulty, but business impact — is a key skill support staff are evaluated on.

---

## The Troubleshooting Process

A structured, repeatable approach used across the industry (not just informally "trying things"):

1. **Identify the problem** — gather details from the user: what happened, when, what changed recently, can it be reproduced.
2. **Establish a theory of probable cause** — based on symptoms and known common causes.
3. **Test the theory** — verify the suspected cause before attempting a fix.
4. **Establish a plan of action** — determine the fix and any potential impact (especially for changes affecting other users/systems).
5. **Implement the solution** — apply the fix, escalating if it requires access or approval beyond your level.
6. **Verify full system functionality** — confirm the issue is actually resolved, not just appearing to be.
7. **Document everything** — what the issue was, what was tried, what worked — for the ticket record and future reference.

This structured approach (closely aligned with CompTIA's troubleshooting methodology) is what separates professional support from guesswork.

---

## Communication Skills

Technical skill alone isn't enough — how an issue is communicated matters just as much in enterprise support:

- **Plain language:** Explaining technical issues and solutions without unnecessary jargon, adjusted to the user's technical level.
- **Setting expectations:** Letting the user know what's being done and roughly how long it will take, rather than leaving them uninformed.
- **Active listening:** Fully understanding the user's description before jumping to a diagnosis — many issues are misdiagnosed because of assumptions made too early.
- **Managing frustration professionally:** Users are often stressed or frustrated when something isn't working — staying calm and solution-focused is expected, regardless of tone from the other side.

---

## Security & Compliance Awareness

In regulated industries (telecom, finance, healthcare), IT support staff are expected to understand and follow data protection and compliance requirements — not just fix technical issues in isolation.

- **Data privacy:** Being cautious with customer/employee data, following the principle of least privilege when granting access.
- **Regulatory awareness:** In Saudi Arabia, this includes frameworks like those from **SDAIA** (Saudi Data & AI Authority) and **CST** (Communications, Space & Technology Commission, formerly CITC) — relevant especially in telecom environments.
- **Incident reporting:** Knowing when a technical issue is actually a security incident (see [Security/Account-Compromise.md](Security/Account-Compromise.md) and [Security/Malware.md](Security/Malware.md)) and needs to be escalated differently than a routine ticket.

---

## Working in Shift-Based Teams

Many enterprise support environments (especially telecom, given 24/7 customer operations) run shift-based coverage:

- **Handover documentation:** Clearly documenting ongoing issues for the next shift, so context isn't lost between teams.
- **On-call rotations:** Higher-tier staff often rotate on-call responsibility for after-hours critical issues.
- **Team coordination:** Tickets may be worked on by multiple people across shifts, making clear documentation (see Ticketing Systems above) essential.

---

## Related

- See [Troubleshooting/](Troubleshooting/) for applied, step-by-step versions of this methodology for specific technical issues.
- See [Security/](Security/) for the security concepts referenced under compliance awareness.
