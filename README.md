# FortiGate CLI configuration examples

This repository contains focused FortiGate CLI examples for common
administration tasks. Each command block is an independent reference snippet,
not a complete configuration to paste into a device.

## Target version

All examples target **FortiOS 8.0.0** and were reviewed on **2026-07-21**
against the Fortinet 8.0.0 Administration Guide and CLI Reference. Older
FortiOS releases are not supported by this repository; use their matching
Fortinet documentation instead of adapting these examples with legacy syntax.

Command availability still depends on the FortiGate model, operating mode,
enabled features, and licensing. Hardware switches, virtual VLAN switches,
trunks, transceiver information, EMAC VLANs, and some acceleration features
are not available on every appliance or FortiGate-VM.

Official FortiOS 8.0.0 references:

- [Administration Guide](https://docs.fortinet.com/document/fortigate/8.0.0/administration-guide)
- [CLI Reference](https://docs.fortinet.com/document/fortigate/8.0.0/cli-reference)
- [Release Notes](https://docs.fortinet.com/document/fortigate/8.0.0/fortios-release-notes)

## Repository contents

| File | Examples included |
| --- | --- |
| [`FortiGateAdminSetup.conf`](FortiGateAdminSetup.conf) | Version checks, initial access, management interface settings, hostname, default route, connectivity checks, FortiCloud activation, and factory resets. |
| [`FortiGateAdminInterfaces.conf`](FortiGateAdminInterfaces.conf) | Physical interfaces, VLANs, address objects, firewall policies, NAT, hardware and software switches, trunks, aggregate and redundant interfaces, FortiOS 8.0.0 software-switch 802.1X, zones, virtual wire pairs, and EMAC VLANs. |
| [`FortiGateAdminDHCP.conf`](FortiGateAdminDHCP.conf) | DHCP server pools, DHCP relay configuration, and disabling an existing DHCP server. |
| [`FortiGateAdminDNS.conf`](FortiGateAdminDNS.conf) | System and VDOM DNS, primary DNS databases, recursive DNS service, DDNS, DNS over TLS and HTTPS, and FortiOS 8.0.0 DNS over QUIC and HTTP/3. |
| [`FortiGateAdminBackups.conf`](FortiGateAdminBackups.conf) | FortiOS 8.0.0 configuration backup and restore with SCP, management-station revisions, flash, USB, FTP, TFTP, SFTP backup, YAML, and full or obfuscated exports. |
| [`FortiGateAdminCerts.conf`](FortiGateAdminCerts.conf) | Secure SCP export, import, and verification of local certificates. |
| [`SECURITY.md`](SECURITY.md) | Supported content, private reporting guidance, project scope, and safe-use recommendations. |

## Using the examples

1. Run `get system status` and confirm that the device is running FortiOS
   8.0.0.
2. Find the individual block that matches the task; do not paste an entire
   `.conf` file.
3. Check the feature and model in the FortiOS 8.0.0 documentation. At the
   relevant CLI prompt, use `?` or `tree <branch>` to confirm availability.
4. Replace every placeholder and illustrative value with values for the target
   environment.
5. Confirm that referenced interfaces, VDOMs, certificates, user groups,
   security profiles, and address objects exist. Remove interfaces from
   conflicting policies, zones, switches, aggregates, or virtual wire pairs
   before reassigning them.
6. Back up the device, test the change outside production, and inspect CLI
   output for `Command fail`, `parse error`, `node_check_object`, and
   `entry not found` messages. FortiOS can accept part of a pasted block while
   rejecting later lines.

Notation such as `<value>`, `{choice-a | choice-b}`, and `[optional-value]`
describes values or alternatives and must not be pasted literally. IP
addresses, interface names, VDOMs, policy IDs, and object names are examples.

## Important cautions

- Applying a block without checking the existing configuration can replace an
  object with the same name or ID.
- Policies using `service "ALL"`, broad address objects, or permissive
  management access are demonstrations. Apply least privilege in production.
- Restrict administrative access with trusted hosts, a dedicated management
  interface, and local-in policies where appropriate.
- Backup and restore commands can expose credentials in terminal history,
  recordings, or logs. Prefer SCP and protect configuration backups and
  PKCS#12 files with strong passwords.
- FTP and TFTP do not encrypt data in transit. Use them only on an isolated
  management network when SCP is unavailable.
- Restoring a configuration replaces the active configuration and normally
  restarts the FortiGate. The backup must match the device model and FortiOS
  version.
- `execute factoryreset` and `execute factoryreset2` are destructive. Confirm
  the device and maintain a tested backup before using either command.
- Never commit production passwords, tokens, private keys, certificates, or
  unsanitized FortiGate configuration backups.

This is an independent community reference, not an official Fortinet
repository. Report repository security concerns through
[`SECURITY.md`](SECURITY.md).
