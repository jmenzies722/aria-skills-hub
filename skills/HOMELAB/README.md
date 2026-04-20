# HOMELAB Skill

A guided, interactive OS for designing, building, and operating a self-hosted infrastructure lab — powered by Claude Code.

## Install

```bash
mkdir -p ~/.claude/skills/HOMELAB && \
curl -fsSL https://raw.githubusercontent.com/jmenzies722/aria-skills-hub/main/skills/HOMELAB/skill.md \
  -o ~/.claude/skills/HOMELAB/skill.md
```

## Trigger

```
/homelab
```

Or say: `homelab setup`, `self-host`, `proxmox`, `rack build`, `home server`

## Routes

| # | Route | What you get |
|---|-------|-------------|
| 1 | Design | Hardware recommendations, network topology, VLAN plan, power estimate |
| 2 | Services | Curated catalog — infrastructure, networking, storage, AI/dev, observability |
| 3 | Deploy | `docker-compose.yml`, Traefik labels, Proxmox LXC commands, k8s manifests |
| 4 | Status | Live audit of containers, disk, ports, reachable hosts |
| 5 | Learn | Deep-dive any concept (ZFS, Tailscale, SSO, VLANs, etc.) |
| 6 | Save | Writes lab state to Obsidian + Notion activity log |

## Opinionated Starter Stack

The skill recommends this path for engineers new to homelabbing:

1. **Proxmox VE** — type-1 hypervisor, runs VMs + LXC containers
2. **Tailscale** — zero-friction remote access, works behind CGNAT
3. **Ollama + Open WebUI** — local LLM inference (Llama 3, Mistral)
4. **Traefik + Authentik** — reverse proxy + SSO for all services
5. **Grafana + Prometheus** — observability stack
6. **Uptime Kuma** — service health dashboard

## Customization

Edit `~/.claude/skills/HOMELAB/skill.md` directly:

- Change the Obsidian vault path from `~/Documents/Obsidian Vault` to yours
- Add your own services to the catalog
- Swap Notion logging for any other tool (just remove those sections)

## Full docs

[aria-skills-hub README](../../README.md)
