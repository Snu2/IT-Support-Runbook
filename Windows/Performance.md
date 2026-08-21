# Windows Performance

Reference guide covering how to assess Windows system performance, key resources to monitor, and common performance troubleshooting concepts.

---

## The Four Core Resources

Nearly all performance issues trace back to one (or more) of these four resources being overloaded:

| Resource | What It Affects | Key Tool |
|---|---|---|
| CPU | How fast the system processes tasks | Task Manager, Performance Monitor |
| Memory (RAM) | How many programs can run smoothly at once | Task Manager, Resource Monitor |
| Disk | How fast files are read/written | Resource Monitor, Task Manager |
| Network | How fast data moves to/from the internet or LAN | Task Manager, Resource Monitor |

A slow system is almost always caused by one of these hitting its limit — identifying which one is the first step in any performance investigation.

---

## Key Diagnostic Tools

- **Task Manager:** Quick overview of CPU, memory, disk, and network usage, plus which processes are consuming the most resources.
- **Resource Monitor (`resmon`):** A deeper view than Task Manager, showing per-process disk and network activity in detail.
- **Performance Monitor (`perfmon`):** Allows tracking specific performance counters over time, useful for spotting trends or intermittent issues.
- **Event Viewer:** Won't show performance stats directly, but can reveal errors or warnings that correlate with performance drops (e.g., driver crashes, disk errors).

---

## Key Performance Concepts

- **Bottleneck:** The single resource limiting overall system performance — even if other resources have room to spare, the bottlenecked one determines how fast the system feels.
- **Startup Programs:** Applications configured to launch automatically when Windows boots — too many can significantly slow down startup and background performance.
- **Background Processes:** Programs or services running without a visible window, which can still consume significant CPU, memory, or disk resources.
- **Virtual Memory (Page File):** Disk space used as an overflow when RAM is full — relying on it heavily (due to low RAM) significantly slows performance since disk is much slower than RAM.
- **Disk Fragmentation:** On traditional HDDs, files split into scattered pieces can slow read/write speed (not a concern on SSDs, which don't benefit from defragmentation).

---

## Common Performance Issues

- **System slow overall:** Check Task Manager first to identify whether CPU, memory, or disk is maxed out, then investigate the specific process responsible.
- **Slow to boot:** Often caused by too many startup programs — review and disable unnecessary ones in Task Manager's Startup tab.
- **High disk usage with no clear cause:** Can be caused by Windows Update, antivirus scans, indexing, or a failing drive — Resource Monitor helps identify the specific process.
- **Memory usage climbing over time:** May indicate a memory leak in a specific application — identify the process in Task Manager and consider restarting it or checking for updates.
- **Sudden performance drop after an update:** Worth checking Event Viewer for driver or compatibility issues introduced by the update.

---

## Related

- See [Windows/Services.md](Services.md) for how background services can affect performance.
- See [Commands/Windows.md](../Commands/Windows.md) for relevant command-line tools (`tasklist`, `wmic`).
