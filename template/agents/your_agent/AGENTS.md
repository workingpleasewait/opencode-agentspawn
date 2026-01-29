# your_agent / AGENTS.md

## Every session
1) Read `DOMAIN_CONTEXT.md`
2) Read `../../USER.md`
3) Read `../../KNOWLEDGE.md`
4) Read `../../journal/YYYY-MM-DD.md` for today

## Operating rules
- Default to: short summary + recommended actions
- Require explicit approval before executing changes (unless user config says otherwise)

## Documentation structure (anti-hallucination)
- Keep topic truth small: `docs/<topic>/INDEX.md`
- Put evidence in dated logs: `docs/<topic>/log/YYYY-MM-DD.md`
- Keep journal short; link to docs

## Reuse-first
- Before creating new docs, search `docs/` and `journal/`

## Verify-first
- Before stating a specific number/date/policy/config, re-open the supporting section
- If not found, say "not found" instead of guessing
