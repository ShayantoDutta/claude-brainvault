# Credential Patterns — Reference

Patterns the skill scans for during Phase 4 (ANALYZE) before writing any vault content.
If matched, content is excluded and user is warned.

## Patterns to detect

```
api_key
apikey
API_KEY
sk-
pk-
Bearer 
password=
passwd=
pwd=
token=
access_token
refresh_token
secret=
client_secret
private_key
-----BEGIN
.env (file extension or filename)
export [A-Z_]+=   (shell env var assignment)
[A-Z_]+=.{8,}    (ALL_CAPS_KEY=longvalue pattern)
```

## High-risk file types to flag immediately

- `.env`, `.env.local`, `.env.production`, `.env.*`
- `*.pem`, `*.key`, `*.p12`, `*.pfx`
- `credentials.json`, `secrets.json`, `config.json` (if contains key-like values)
- `.netrc`
- `id_rsa`, `id_ed25519` (SSH private keys)

## What to do when a pattern is found

1. Stop processing that file/content immediately
2. Warn the user: `⚠️ Found what looks like sensitive data in [source]. Excluded from vault. Please review.`
3. Continue processing all other content
4. Never write flagged content into any vault file
5. Log the exclusion in `_system/evolution_log.tsv` with entry type `SECURITY_EXCLUSION`
