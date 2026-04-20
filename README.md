# ARIA Skills Hub

**Custom Claude Code skills built for engineers who want their AI to actually do things.**

These are production-quality skills for [Claude Code](https://claude.ai/code) — the AI CLI. Each skill turns a natural-language trigger into a guided, multi-step workflow that reads your files, runs commands, calls APIs, and writes results back to your tools.

---

## Skills

| Skill | Trigger | What it does |
|-------|---------|-------------|
| [HOMELAB](./skills/HOMELAB/) | `/homelab` | Design, deploy, and operate a self-hosted infrastructure lab |

> More skills shipping soon. Star the repo to follow along.

---

## HOMELAB Skill

The flagship skill. A full interactive OS for building and running a homelab — from hardware planning to deployed Docker services to live status checks.

**Capabilities:**

| Route | What happens |
|-------|-------------|
| `Design` | Collects your goals, budget, and existing hardware → generates a full network topology + hardware recommendation |
| `Services` | Curated catalog of self-hostable services with Josh-specific AI/dev picks highlighted |
| `Deploy` | Scaffolds ready-to-run `docker-compose.yml`, Traefik labels, Proxmox LXC commands, k8s manifests |
| `Status` | Audits running containers, disk usage, exposed ports, and reachable lab hosts |
| `Learn` | Explains any homelab concept (VLANs, ZFS, Tailscale, SSO, observability) in depth |
| `Save` | Writes your lab state to Obsidian + logs to Notion |

**Works best with:**
- [Claude Code](https://claude.ai/code) (required)
- Obsidian (optional — for lab notes)
- Notion (optional — for activity logging)
- Docker on your lab host

---

## Installation

### Option 1 — One-liner (recommended)

```bash
mkdir -p ~/.claude/skills/HOMELAB && \
curl -fsSL https://raw.githubusercontent.com/joshmenzies/aria-skills-hub/main/skills/HOMELAB/skill.md \
  -o ~/.claude/skills/HOMELAB/skill.md
```

Restart Claude Code. The skill auto-registers.

### Option 2 — Clone the repo

```bash
git clone https://github.com/joshmenzies/aria-skills-hub.git ~/aria-skills-hub
mkdir -p ~/.claude/skills/HOMELAB
cp ~/aria-skills-hub/skills/HOMELAB/skill.md ~/.claude/skills/HOMELAB/skill.md
```

### Option 3 — Manual

1. Download [`skills/HOMELAB/skill.md`](./skills/HOMELAB/skill.md)
2. Place it at `~/.claude/skills/HOMELAB/skill.md`
3. Restart Claude Code

---

## Usage

Once installed, trigger the skill in Claude Code by typing any of:

```
/homelab
homelab setup
home lab
self-host
proxmox
rack build
```

Claude Code reads the trigger and loads the full skill prompt automatically.

### Example session

```
You:   /homelab

ARIA:  HOMELAB OS
       1  Design    — plan hardware + network topology
       2  Services  — pick and configure what to run
       3  Deploy    — scaffold configs, docker-compose, k8s
       4  Status    — audit running lab + health check
       5  Learn     — explain a homelab concept
       6  Save      — write current state to Obsidian

You:   1

ARIA:  What's your goal? (learning / self-hosting apps / AI workloads / network lab)

You:   AI workloads + self-hosting, budget ~$1000

ARIA:  [generates full architecture recommendation]
```

---

## Requirements

- **Claude Code** — the CLI (`npm install -g @anthropic-ai/claude-code` or download from claude.ai/code)
- macOS or Linux (skill uses bash commands)
- Docker (for Deploy + Status routes)
- Optional: Obsidian, Notion, Tailscale

---

## Customization

The skill is a single markdown file — edit it to fit your setup:

| Section | What to change |
|---------|---------------|
| Obsidian vault path | Change `~/Documents/Obsidian Vault` to your vault location |
| Notion database ID | Replace `bfd3a8a3-...` with your Activity Log DB ID |
| Hardware tiers | Add your own hardware to the budget tiers |
| Services catalog | Add services relevant to your stack |

---

## Roadmap

- [ ] `HOMELAB Pro` — advanced routes: BGP lab, k8s cluster provisioning, GPU passthrough
- [ ] Companion web app — AI-powered config generator (no Claude Code required)
- [ ] `DEVLAB` skill — spins up isolated dev environments with Docker + Caddy
- [ ] `NETLAB` skill — network simulation, VLAN design, OPNsense config generator
- [ ] Skills installer CLI — `aria install homelab`

---

## Contributing

PRs welcome. See [CONTRIBUTING.md](./CONTRIBUTING.md).

If you add a service to the catalog or a hardware tier, open a PR — the community benefits.

---

## Pro Version

A **HomelabOS** web app is in the works — AI-powered homelab config generator that doesn't require Claude Code. Early access list: [joshmenzies.dev/homelab](https://joshmenzies.dev/homelab) *(coming soon)*

Features planned for Pro:
- Visual network topology builder
- One-click docker-compose generation for any service stack
- Automated `docker compose up` via SSH to your lab host
- Uptime monitoring dashboard
- Config version history

---

## License

MIT — use it, fork it, build on it.

---

## Author

**Josh Menzies** — Platform Engineer, AWS certified, building AI infrastructure at [Nectar](https://gonectar.com).

- GitHub: [@joshmenzies](https://github.com/joshmenzies)
- Built with: Claude Code · Anthropic SDK · AWS · Terraform

---

*If this saved you time, star the repo. It helps.*
