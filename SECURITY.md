# Security Policy

## Scope

This repository documents an educational cybersecurity lab. It is not a production service or authorization to test third-party systems.

## If Sensitive Data Is Exposed

1. Remove the exposed material and rotate/revoke the affected credential.
2. Review repository history; deleting a file from the latest commit does not remove it from Git history.
3. Do not include passwords, tokens, private keys, VPN profiles, or personal data in public issues.

## Never Commit

- `.env` files or database connection strings
- `.pem`, `.key`, private certificates, VPN `.ovpn` profiles
- API keys, Splunk HEC tokens, JWTs, cookies, or session data
- Database dumps, backups, or raw logs with sensitive information
- Unredacted screenshots exposing credentials or unnecessary live infrastructure details
