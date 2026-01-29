# Companion: opencode-architect + opencode-agentspawn

This doc explains how to use `opencode-agentspawn` (workspace template) alongside `qforge-dev/opencode-architect` (OpenCode plugin).

## TL;DR
- Use **agentspawn** for the durable, versioned workspace structure (docs, journal, INDEX/log pattern, reuse-first/verify-first rules).
- Use **opencode-architect** when you want extra OpenCode tooling while you *author* agents/plugins/commands and keep OpenCode docs synced.

They solve different problems and work well together.

## What each project does
### opencode-agentspawn (this repo)
- A template + playbook for an agent’s workspace “brain”
- Focus: long-term reliability and collaboration
  - INDEX.md stays small (canonical truth)
  - logs can grow (evidence)
  - reuse-first + verify-first reduce duplicate work and hallucinations

### opencode-architect (plugin)
- An OpenCode plugin that adds helpers for building OpenCode agents/plugins/commands/tools
- Includes a `sync-docs` workflow to keep OpenCode documentation up-to-date

## Recommended workflow (how to combine)
1) Create your agent workspace repo using this template
   - Copy `template/` into the repo root
   - Rename placeholders (`<agent_name>`, `<topic>`, etc.)
2) Wire your agent into OpenCode via `~/.config/opencode/opencode.json`
   - Recommended: configure your specialist as a **subagent** so you can summon it via `@<agent_name>` while keeping your main agent selected
   - See `examples/opencode.json.snippets.jsonc`
3) (Optional) Install `opencode-architect` in the project when you’re actively building OpenCode things
   - It may add additional agents/commands to your UI (by design)

## Notes
- If you want a minimal agent picker/UI, you might skip plugin installs (or install them only in dedicated repos).
- Even if you use `opencode-architect`, you still want the agentspawn workspace rules to prevent drift and context bloat over time.
