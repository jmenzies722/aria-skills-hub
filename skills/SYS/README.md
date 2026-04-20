# SYS Skill

Machine health pipeline for Claude Code. Scan, optimize, monitor, and harden your local machine — all from a single trigger.

## Install

```bash
mkdir -p ~/.claude/skills/SYS && \
curl -fsSL https://raw.githubusercontent.com/jmenzies722/aria-skills-hub/main/skills/SYS/skill.md \
  -o ~/.claude/skills/SYS/skill.md
```

## Trigger

```
/sys
```

Or say: `machine health`, `optimize my machine`, `what's eating my CPU`, `clean up my mac`, `system check`

## Routes

| # | Route | What you get |
|---|-------|-------------|
| 1 | Scan | Full audit — CPU, RAM, disk, swap, caches — scored 1–10 with top process breakdown |
| 2 | Optimize | Kill CPU hogs, purge caches (brew, npm, pip, Safari), measure before/after delta |
| 3 | Monitor | Live metrics loop refreshing every 30s — CPU, memory, disk I/O |
| 4 | Report | Write findings to Obsidian + log to Notion Activity Log |
| 5 | Harden | Install a launchd plist for weekly automated scans → Telegram notification |

## Example output

```
MACHINE HEALTH — 2026-04-20 09:14

CPU       12%     9/10   top hog: Slack (4.2%)
RAM       6.1GB free / 16GB   8/10
Disk      142GB free / 500GB  9/10
Swap      0GB used            10/10
Caches    3.8GB               6/10

OVERALL   8.4/10

BIGGEST WINS IF OPTIMIZED
▸ Clear 3.8GB caches — ~10 min
▸ Kill Slack background processes
```

## Requirements

- [Claude Code](https://claude.ai/code)
- macOS (uses `vm_stat`, `top`, `osascript`)
- Optional: Obsidian, Notion, Telegram (for Harden route)
