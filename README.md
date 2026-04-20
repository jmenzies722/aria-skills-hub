# ARIA Skills Hub

Custom Claude Code skills for engineers. Each skill turns a natural-language trigger into a guided, multi-step workflow — reads files, runs commands, calls APIs, writes results back to your tools.

---

## Skills

| Skill | Trigger | What it does |
|-------|---------|-------------|
| [HOMELAB](./skills/HOMELAB/) | `/homelab` | Design, deploy, and operate a self-hosted infrastructure lab |
| [SYS](./skills/SYS/) | `/sys` | Machine health pipeline — scan, optimize, monitor, and harden your Mac |

---

## Install All Skills

```bash
# HOMELAB + SYS in one shot
for skill in HOMELAB SYS; do
  mkdir -p ~/.claude/skills/$skill
  curl -fsSL https://raw.githubusercontent.com/jmenzies722/aria-skills-hub/main/skills/$skill/skill.md \
    -o ~/.claude/skills/$skill/skill.md
done
```

---

## HOMELAB

A full interactive OS for building and running a homelab — hardware planning, Docker service setup, live status checks, and more.

| Route | What happens |
|-------|-------------|
| `Design` | Collects your goals, budget, and existing hardware → generates a network topology + hardware recommendation |
| `Services` | Curated catalog of self-hostable services (infra, networking, storage, AI, observability) |
| `Deploy` | Scaffolds ready-to-run `docker-compose.yml`, Traefik labels, Proxmox LXC commands, k8s manifests |
| `Status` | Audits running containers, disk usage, exposed ports, and reachable lab hosts |
| `Learn` | Explains any homelab concept (VLANs, ZFS, Tailscale, SSO, observability) |
| `Save` | Writes your lab state to Obsidian + logs to Notion |

---

## Installation

### One-liner

```bash
mkdir -p ~/.claude/skills/HOMELAB && \
curl -fsSL https://raw.githubusercontent.com/jmenzies722/aria-skills-hub/main/skills/HOMELAB/skill.md \
  -o ~/.claude/skills/HOMELAB/skill.md
```

Restart Claude Code. The skill auto-registers.

### Clone

```bash
git clone https://github.com/jmenzies722/aria-skills-hub.git
mkdir -p ~/.claude/skills/HOMELAB
cp aria-skills-hub/skills/HOMELAB/skill.md ~/.claude/skills/HOMELAB/skill.md
```

---

## Usage

```
/homelab
homelab setup · self-host · proxmox · rack build
```

---

## Requirements

- [Claude Code](https://claude.ai/code)
- macOS or Linux
- Docker (for Deploy + Status routes)
- Optional: Obsidian, Notion

---

## Customization

Edit `~/.claude/skills/HOMELAB/skill.md` directly:

| What | Where |
|------|-------|
| Obsidian vault path | Change `~/Documents/Obsidian Vault` to your path |
| Notion database ID | Replace `bfd3a8a3-...` with your own |
| Hardware tiers | Add your hardware to the budget table |
| Services catalog | Add services relevant to your stack |

---

## SYS

Machine health pipeline. One trigger gives you a full audit, optimization run, and optional weekly automated scan.

| Route | What happens |
|-------|-------------|
| `Scan` | CPU, RAM, disk, swap, caches — scored 1–10, top processes listed |
| `Optimize` | Kill hogs, purge caches (brew/npm/pip), before/after delta |
| `Monitor` | Live metrics loop, refreshes every 30s |
| `Report` | Findings → Obsidian + Notion |
| `Harden` | Weekly launchd scan → Telegram notification |

---

## Contributing

PRs welcome. See [CONTRIBUTING.md](./CONTRIBUTING.md).

---

## License

MIT

---

**Josh Menzies** · [@jmenzies722](https://github.com/jmenzies722)
