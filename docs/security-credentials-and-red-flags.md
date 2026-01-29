# Security: Credentials and Red Flags

## Never commit secrets
Do not store any of the following in git:
- access keys / secret keys / session tokens
- passwords
- MFA seeds
- private keys
- `.env` files

## Where credentials should live instead
- Official CLI/SDK auth flows
- OS credential store/keychain
- environment variables

## Red flags
- Copy/pasting raw console exports into docs without reviewing
- Committing "temporary" credentials
- Mixing personal account identifiers into public templates

## Recommendation
Before pushing to GitHub, do a quick scan for obvious secrets (even a simple grep).
