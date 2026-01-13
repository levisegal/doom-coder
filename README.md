# Doom Coder

A control plane for [doom coding](https://github.com/rberg27/doom-coding) - productive mobile development using Claude Code from anywhere.

## Concept

"Doom coding" flips doom scrolling into something productive: using your phone to code via SSH while away from your desk. This repo serves as the control plane for managing Claude Code sessions remotely.

## Setup

### Prerequisites

- Mac/Linux machine running 24/7 with SSH enabled
- [Tailscale](https://tailscale.com/) installed on both machine and phone
- [Termius](https://termius.com/) (or other mobile SSH client) on phone
- [Claude Code](https://claude.ai/download) installed on the machine

### Network

Tailscale creates a secure mesh network between your devices. Access your machine via MagicDNS:

```
ssh user@machine-name.tailnet-name.ts.net
```

### Web Previews

Run a dev server and view it on your phone's browser:

```
http://machine-name.tailnet-name.ts.net:3000
```

## Workflow

1. SSH into the machine from Termius
2. Use `bd` (beads) to manage work items and track progress
3. Run Claude Code to implement features
4. Preview changes in mobile browser via Tailscale

## Tools

- **[beads](https://github.com/anthropics/beads) (`bd`)** - Lightweight issue tracking with dependency support
- **Claude Code** - AI-assisted development from the terminal

## Quick Reference

```bash
bd ready              # Find available work
bd show <id>          # View issue details
bd update <id> --status in_progress  # Claim work
bd close <id>         # Complete work
bd sync               # Sync with git
```

See `AGENTS.md` for full agent workflow instructions.
