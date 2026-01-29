# opencode-agentspawn

A public **template repo + playbook** for spawning reliable agent workspaces.

Designed for **OpenCode** first, but reusable anywhere: the durable value is the workspace structure, memory hygiene, and safety rules.

**Important:** this is **not** an OpenCode plugin. It won’t automatically add new agents to your OpenCode UI by itself.
Instead, it gives you a workspace template + config snippets so you can wire your own agents in a clean, repeatable way.

## What this gives you
- A copyable workspace skeleton under `template/`
- Practical rules so agents:
  - **don’t repeat work** (reuse-first)
  - **don’t hallucinate** (verify-before-claiming + INDEX/log structure)
  - **don’t leak secrets** (credential hygiene)
- An opinionated workflow: keep a primary orchestrator agent, then summon specialists via `@your_subagent`

## Quickstart (recommended)
1) Click **Use this template** on GitHub (or fork/clone).
2) Copy `template/` into your new workspace repo (or use it as the repo root).
3) Rename placeholders:
   - `template/agents/your_agent/` → `agents/<your_agent_name>/`
   - `template/docs/topic/` → `docs/<your_topic>/` (add more topics as needed)
4) Create a persistent prompt on your machine (example path):
   - `~/.config/opencode/prompts/<your_agent_name>.txt`
5) Wire your agent into OpenCode (global config) using **subagent** mode so you can invoke it via `@<your_agent_name>` while keeping your primary agent selected.
   - See `examples/opencode.json.snippets.jsonc`

## The core pattern (why this works)
### Workspace is the durable brain
Keep long-lived context in your repo (versioned):
- `agents/<agent_name>/AGENTS.md` → operating rules + boot order
- `agents/<agent_name>/*_CONTEXT.md` → stable domain context (no secrets)
- `KNOWLEDGE.md` → curated, durable truths
- `journal/YYYY-MM-DD.md` → short daily log + links
- `docs/<topic>/INDEX.md` → canonical short "current truth"
- `docs/<topic>/log/YYYY-MM-DD.md` → deep evidence / raw output

### Prevent hallucinations with INDEX + logs
Agents should treat `docs/<topic>/INDEX.md` as the only thing that stays small enough to be reliable. Everything else goes into dated logs.

### Reuse-first + verify-first
- **Reuse-first:** search existing docs before creating a new doc
- **Verify-first:** before stating a specific number/date/policy/config, re-open the supporting section

## Safety / credentials
Do **not** commit secrets. This repo contains only patterns and placeholders.
See `docs/security-credentials-and-red-flags.md`.

## Optional: oh-my-opencode
If you use the `oh-my-opencode` plugin, great — this template still works.
See `examples/oh-my-opencode.json.example`.

## Related projects
- `qforge-dev/opencode-architect` — an OpenCode plugin that adds agent-building helpers and doc sync tooling. Useful companion if you’re actively developing OpenCode agents/plugins: https://github.com/qforge-dev/opencode-architect

## Contributing
Advanced contributors welcome. See `CONTRIBUTING.md`.

## License
MIT — see `LICENSE`.
