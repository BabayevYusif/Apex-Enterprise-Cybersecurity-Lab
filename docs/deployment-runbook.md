# Deployment and Operational Runbook

This is a safe operational checklist for the existing lab. It is not a one-click installer and contains no credentials.

## Documented Application Paths

```text
/srv/apex/
├── external/
│   ├── frontend/
│   └── backend/
├── intranet/
│   ├── frontend/
│   └── backend/
├── shared/
└── backups/
```

The project notes mention a protected shared secrets location. Do not commit its contents.

## Basic Health Checks

Run on the relevant server with an authorized account:

```bash
sudo systemctl status nginx --no-pager
sudo systemctl status postgresql --no-pager
pm2 list
pm2 logs apex-external-backend --lines 50
pm2 logs apex-intranet-backend --lines 50
sudo fail2ban-client status
sudo ss -tulnp
```

A backend health endpoint was documented in the project. Verify the current local port and path from the active Nginx/backend configuration before using a curl command.

## Nginx Change Procedure

1. Back up the current site configuration.
2. Edit only the intended virtual host.
3. Run `sudo nginx -t`.
4. Reload Nginx only if the syntax check succeeds.
5. Re-test the external site and VPN-only intranet.
6. Review logs for unexpected 4xx/5xx responses.

## Node.js / PM2

- Keep `.env` readable only by the service account/root as appropriate.
- Do not paste environment values into terminal screenshots.
- Confirm PM2 startup persistence after changes.
- Review application logs after deployment or restart.
- Rebuild the frontend when source assets change, then deploy the verified build.

## PostgreSQL / VPN / Splunk

- Verify PostgreSQL is not listening on a public interface; test backups and restoration.
- Never upload `.sql` dumps or backups containing user data.
- Never upload `.ovpn` profiles, CA private keys, TLS keys, or client private keys.
- Confirm WAF and IPS/IDS indexes have recent events; verify the ML output is ingested once.
- Check dashboard counts against raw searches before a demo.
