# Windows Printers

Reference guide covering how printing works on Windows, printer types, and common printer-related concepts.

---

## How Printing Works

When a document is sent to print, Windows hands it off to the **Print Spooler** service, which queues the job and manages communication with the printer. Understanding this flow helps pinpoint where a print job might be failing.

**Basic flow:**
1. User sends a print job from an application
2. The **Print Spooler** service receives and queues the job
3. The spooler formats the job using the correct **printer driver**
4. The job is sent to the printer via its connection (USB, network, etc.)
5. The printer processes and prints the job

If any step in this chain fails, the print job can get stuck, disappear, or produce garbled output.

---

## Printer Connection Types

| Type | Description |
|---|---|
| Local (USB) | Printer connected directly to one computer |
| Network Printer | Printer with its own IP address, accessible by any device on the network |
| Shared Printer | A locally connected printer shared from one computer for others to use |
| Cloud Print | Printing managed through a cloud service rather than direct network discovery |

---

## Key Printer Concepts

- **Print Spooler:** The Windows service that manages the print queue — most printing issues start with checking whether this service is running.
- **Printer Driver:** Software that translates print jobs into a format the specific printer model understands. Outdated or mismatched drivers are a common cause of print failures.
- **Print Queue:** The list of pending print jobs — a stuck job at the top of the queue can block all jobs behind it.
- **Default Printer:** The printer automatically selected when printing unless another is manually chosen.
- **Printer Sharing:** Allows one printer connected to a single computer to be used by others on the network, though this depends on that computer staying powered on.

---

## Common Printer Issues

- **Print job stuck in queue:** Usually resolved by clearing the queue and restarting the Print Spooler service.
- **Printer shows "offline":** Check the physical/network connection first, then confirm the printer's IP hasn't changed (common with DHCP-assigned printers).
- **Garbled or incorrect output:** Often a driver mismatch — reinstalling or updating the correct driver typically resolves this.
- **Can't find network printer:** Verify the printer and computer are on the same network/subnet, and that network discovery is enabled.
- **"Access denied" when printing:** Points to a permissions issue — check that the user has print permissions on that specific printer.

---

## Related

- See [Windows/Services.md](Services.md) for more on the Print Spooler service.
- See [Commands/Windows.md](../Commands/Windows.md) for relevant command-line tools (`net use`, printer troubleshooting via `printui.exe`).
