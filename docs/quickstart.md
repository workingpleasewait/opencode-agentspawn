# Quickstart

## Goal
Create a new agent workspace repo that stays fast and accurate over time.

## Steps
1) Create a new repo from this template (GitHub: "Use this template").
2) Copy `template/` contents into your new repo root.
3) Rename placeholder folders:
   - `agents/your_agent/` → `agents/<your_agent_name>/`
   - `docs/topic/` → `docs/<your_topic>/` (add more topics as needed)
4) Create a persistent prompt on your machine:
   - `~/.config/opencode/prompts/<your_agent_name>.txt`
5) Add the agent to `~/.config/opencode/opencode.json` as a **subagent** (recommended).
6) In OpenCode, keep your preferred primary agent selected and invoke the specialist as:
   - `@<your_agent_name> ...`

See `examples/opencode.json.snippets.jsonc`.
