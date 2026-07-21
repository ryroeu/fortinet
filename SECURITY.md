# Security Policy

## Supported Versions

This repository contains FortiGate configuration examples rather than
versioned software releases.

| Content | Supported |
| --- | --- |
| Current `main` branch | ✅ |
| Earlier commit snapshots or modified copies | ❌ |

Security-related corrections are made only to the current `main` branch.

## Reporting a Security Issue

If you discover a security issue in this repository, please do **not** open a
public issue containing sensitive details.

Use GitHub's **Report a vulnerability** option under the repository's
**Security and quality** tab:

https://github.com/ryroeu/fortinet/security/advisories

A useful report should include:

- The affected file and command or configuration block
- The relevant FortiGate model and FortiOS version, if known
- The potential security impact
- Steps to reproduce or demonstrate the issue
- A suggested correction or safer configuration, if available

Do not include production credentials, private keys, complete device
configurations, public IP addresses, or other sensitive customer information.
Sanitize all examples before submitting them.

Reports will be reviewed on a best-effort basis. Please allow time to
investigate and coordinate a correction before publicly disclosing the issue.

## Scope

Appropriate reports include:

- Credentials, keys, or other secrets accidentally committed to this repository
- Commands that unintentionally expose administrative services or data
- Insecure configuration examples that could create a material security risk
- Incorrect security guidance within the repository

General documentation corrections and non-sensitive mistakes may be submitted
as normal GitHub issues or pull requests.

## Fortinet Product Vulnerabilities

This is an independent community repository and is not an official Fortinet
repository.

Suspected vulnerabilities in Fortinet products or services should be reported
directly to the [Fortinet Product Security Incident Response Team
(PSIRT)](https://www.fortiguard.com/psirt_policy).

## Safe Use of These Examples

The files in this repository are reference examples. Before applying them:

- Verify every command against the documentation for your FortiOS version
- Replace placeholders and example addresses with environment-specific values
- Remove or restrict unnecessary administrative access
- Use least-privilege accounts and trusted management networks
- Back up the existing configuration
- Test changes in a non-production environment

Never commit real passwords, API tokens, private keys, certificates, or
unsanitized device backups to this repository.
