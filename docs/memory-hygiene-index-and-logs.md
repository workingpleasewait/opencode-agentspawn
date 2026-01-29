# Memory Hygiene: INDEX + Logs (and why it prevents hallucinations)

## Problem
As docs grow, agents will eventually stop reliably "holding" the whole thing and start guessing.

## Solution
Use a two-layer structure per topic:
- `docs/<topic>/INDEX.md` → canonical short "current truth" (keep concise)
- `docs/<topic>/log/YYYY-MM-DD.md` → deep evidence / raw outputs (can grow without breaking reliability)

## Required behavior
- **Reuse-first:** search before writing a new doc
- **Verify-first:** before stating a specific number/date/policy/config, re-open the supporting section

## Journal rule
Keep `journal/YYYY-MM-DD.md` short and mostly links.
