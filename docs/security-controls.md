# Security Controls and Verification Matrix

| Control | Implementation | Purpose | Evidence |
|---|---|---|---|
| WAF | SafeLine WAF | Filters suspicious HTTP requests and applies blocking rules | Sanitized rule/event screenshots |
| Reverse proxy | Nginx | Routes requests to frontend/API services | Redacted config and `nginx -t` result |
| Password storage | bcrypt | Avoids plaintext password storage | Redacted code/schema evidence |
| Authentication | Express API and JWT | Authenticated API access | Redacted endpoint tests; never publish tokens |
| Input validation | Backend validation | Rejects malformed or weak registration values | Safe validation tests |
| Database isolation | PostgreSQL private/loopback access | Reduces direct database exposure | Sanitized bind/firewall evidence |
| TLS | Let's Encrypt / Certbot | Encrypts browser-to-server traffic | Certificate status, never private keys |
| VPN | OpenVPN | Restricts intended intranet network path | Connection status with profile details hidden |
| Host firewall | UFW + AWS Security Groups | Limits reachable services | Sanitized inbound-rule table |
| Abuse controls | Fail2Ban custom jails | Blocks repeated login, registration, 403/404 and SSH abuse | Redacted jail status |
| Endpoint protection | Bitdefender GravityZone | Endpoint monitoring and protection | Managed endpoint/policy screenshots |
| Honeypot | T-Pot | Observes interactions with decoy services | Redacted attack-map evidence |
| Incident handling | Zammad | Tracks incidents, SLA and TP/FP classification | Template/SLA screenshots |
| ML analytics | Python pipeline | Flags anomalous WAF + IPS/IDS events | Sanitized JSON and Splunk search |

## Verify Before Claiming Complete

- Confirm SafeLine-to-Splunk ingestion and exact index name.
- Confirm Suricata/IPS/IDS events arrive at useful volume.
- Verify the ML job does not ingest the same output twice.
- Verify dashboard totals against raw search results.
- Re-test CSP and anti-clickjacking headers.
- Confirm whether Splunk alerts create Zammad tickets automatically.
- Confirm scanner allowlisting only for approved Nessus/Acunetix testing.
- Do not claim a control is fully effective based on one screenshot.

Redact passwords, tokens, cookies, VPN profiles, private keys, public IPs where unnecessary, and endpoint identifiers.
