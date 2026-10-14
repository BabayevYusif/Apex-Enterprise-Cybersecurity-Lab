# Configuration Examples

Store sanitized templates, not live configurations. Replace real hostnames, IPs, credentials, certificate paths, and tokens with placeholders.

Potential examples: Nginx virtual-host templates, Fail2Ban filters/jails, Splunk input examples with tokens removed, and PM2/systemd examples with environment values omitted.

Never commit `.env`, `.ovpn`, `.pem`, `.key`, production credentials, or a full live server configuration without reviewing it for sensitive details.
