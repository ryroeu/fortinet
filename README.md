# FortiGate CLI configuration examples

This repository is a collection of FortiGate CLI examples for common
administration tasks. The files are organized by topic and are intended as
reference snippets—not as a complete configuration to apply to a device.

## Repository contents

| File | Examples included |
| --- | --- |
| [`FortiGateAdminSetup.conf`](FortiGateAdminSetup.conf) | Initial access, management interface settings, hostname, default route, connectivity checks, FortiGate Cloud activation, and factory-reset commands. |
| [`FortiGateAdminInterfaces.conf`](FortiGateAdminInterfaces.conf) | Physical interfaces, VLANs, address objects, firewall policies, NAT, hardware and software switches, trunks, aggregate and redundant interfaces, 802.1X, zones, virtual wire pairs, and enhanced MAC VLANs. |
| [`FortiGateAdminDHCP.conf`](FortiGateAdminDHCP.conf) | DHCP server pools, DHCP relay configuration, and disabling a DHCP service on an interface. |
| [`FortiGateAdminDNS.conf`](FortiGateAdminDNS.conf) | System and VDOM DNS, DNS databases, recursive DNS service, FortiGuard and generic DDNS, IPv4 and IPv6 DDNS, DHCP-driven DDNS updates, DNS over TLS, and DNS over HTTPS. |
| [`FortiGateAdminBackups.conf`](FortiGateAdminBackups.conf) | Configuration backup and restore commands for a management station, USB, FTP, TFTP, SFTP, and YAML, plus enabling administrative SCP. |
| [`FortiGateAdminCerts.conf`](FortiGateAdminCerts.conf) | Exporting and importing local certificates with TFTP. |
| [`SECURITY.md`](SECURITY.md) | Supported content, private reporting guidance, project scope, and safe-use recommendations. |

## Using the examples

1. Find the individual command block that matches the task.
2. Verify its syntax against the documentation for the target FortiGate model
   and FortiOS release.
3. Replace every placeholder and example value with values appropriate for the
   environment.
4. Back up the current device configuration.
5. Review and test the change in a non-production environment before applying
   it to a production firewall.

Notation such as `<value>`, `{choice-a | choice-b}`, `[optional-value]`, and
`...` describes values or alternatives and must not be pasted literally. IP
addresses, interface names, object names, VDOMs, policy IDs, and other values in
the examples are illustrative.

## Important cautions

- FortiOS commands and available options can differ by FortiOS release, device
  model, operating mode, enabled features, and licensing.
- The files contain independent examples that may reuse object or policy IDs.
  Applying a block without checking the existing configuration can modify an
  existing object.
- Example policies using `service ALL`, permissive management protocols, or
  broad source and destination objects are demonstrations, not hardened
  production recommendations. Restrict access according to least privilege.
- Backup and restore commands may pass credentials as CLI arguments. Avoid
  exposing credentials in shell history, terminal recordings, logs, or Git.
- `execute factoryreset` and `execute factoryreset2` are destructive. Confirm
  the intended device and maintain a tested backup before using either command.
- Never commit production passwords, tokens, private keys, certificates, or
  unsanitized FortiGate configuration backups.

This is an independent community reference and is not an official Fortinet
repository. For product documentation, consult the
[Fortinet Document Library](https://docs.fortinet.com/product/fortigate). For a
security concern involving this repository, follow [`SECURITY.md`](SECURITY.md).
