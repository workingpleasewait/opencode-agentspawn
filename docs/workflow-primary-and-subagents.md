# Workflow: Primary Agent + Mentionable Subagents

## The idea
- Use a **primary** agent as your orchestrator (your day-to-day "driver").
- Configure specialists as **subagents**.
- Invoke specialists on demand via `@specialist`.

## Why
- Keeps your main workflow consistent
- Makes specialists easy to summon
- Reduces context bloat in the primary agent

## When to make something a subagent vs primary
- Subagent (recommended): specialist tools, audits, one-off investigations
- Primary: you want the entire session to live inside that agent

## Practical rule
Specialists should: 
- propose changes
- wait for approval
- and only then execute

(Adjust for your own risk tolerance.)
