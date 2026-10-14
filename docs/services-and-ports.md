# Services and Ports — Reference Checklist

> This is a **reference checklist**, not a verified live firewall export. Confirm listening sockets and AWS Security Group rules before publishing a port inventory. Do not publish unnecessary management endpoints.

| Service | Common / documented port | Intended exposure | Notes |
|---|---|---|---|
| SSH | TCP 22 | Restricted admin sources | Key-based access; Fail2Ban is an extra layer |
| HTTP | TCP 80 | Public web entry if needed | Normally redirects to HTTPS |
| HTTPS | TCP 443 | Public web/WAF-facing entry | Verify which instance receives public traffic |
| OpenVPN | UDP 1194 | Authorized VPN clients | Used for remote intranet access |
| Web origin from WAF | Deployment notes mention TCP 8081 | WAF-to-origin path only | Do not expose origin broadly |
| Intranet service | Notes mention TCP 8080 | VPN/private path only | Must not be public |
| Node.js API | Notes include local TCP 3000 | Loopback/private reverse-proxy path | Nginx should be the controlled entry point |
| PostgreSQL | TCP 5432 | Loopback/private app path only | Never open publicly |
| Splunk | Deployment-specific | Approved admin/forwarder sources | Verify actual Splunk configuration |

## Verify on the Relevant Host

```bash
sudo ss -tulnp
sudo ufw status verbose
sudo systemctl --type=service --state=running
```

Compare output with AWS Security Group inbound rules. A service listening on `0.0.0.0` or `::` may be reachable on more interfaces than intended. Do not paste unredacted output into a public repository.
