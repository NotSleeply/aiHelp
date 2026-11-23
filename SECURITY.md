# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in this repository, please do not disclose it in a public Issue. Report it privately using GitHub Private Vulnerability Reporting (under the repository's **Security** tab) or by contacting the repository maintainers directly.

Please include:

- A description of the vulnerability and its potential impact.
- Minimal steps to reproduce or verify the issue.
- Suggested remediation, if available.

## Contribution Security Rules

All Pull Requests (including AI-assisted submissions) must follow these rules:

- No credential harvesting, hidden telemetry, or unauthorized outbound data exfiltration.
- No obfuscated binaries, unverified external installers, or unexpected privilege escalation.
- Do not modify `.github/workflows` to expose repository secrets or run untrusted `pull_request_target` code.
