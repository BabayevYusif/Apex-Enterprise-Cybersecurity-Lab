# Evidence and Screenshot Guide

## Suggested Evidence Groups

```text
evidence/
├── web-server/
├── safeline-waf/
├── tpot-honeypot/
├── bitdefender-xdr/
├── xdr-policies/
├── zammad-ticketing/
└── splunk-ml/
```

Create these folders when adding screenshots. Use filenames that describe the claim each screenshot proves, for example:

- `01-web-server-nginx-status.png`
- `02-web-auth-registration-test.png`
- `03-waf-block-rule.png`
- `04-xdr-managed-endpoints.png`
- `05-zammad-sla-template.png`
- `06-ml-splunk-result.png`

## Before Uploading

Redact public IPs and unnecessary hostnames; usernames, personal emails and student identifiers; passwords, API keys, bearer/JWT tokens, cookies and environment values; `.pem`, `.key`, `.ovpn`, private certificate material; raw logs containing personal data; AWS account/billing details not required for proof.

Keep enough context to show the tool, setting and result, but not enough to expose access details. Each screenshot should support one clear claim. Do not use a screenshot alone to claim a control is fully effective.
