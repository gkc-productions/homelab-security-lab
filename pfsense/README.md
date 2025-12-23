# pfSense

Scope: document how pfSense is deployed, segmented, and integrated into the observability pipeline.

## What Will Be Documented
- Deployment: VM sizing on Proxmox, interfaces, and storage layout.
- Interface plan: mapping of mgmt/lab/dmz/vpn networks, VLAN IDs, and IP ranges (placeholders until finalized).
- Core services: DHCP/DNS/Resolver settings, NAT policies, and port forwards.
- Firewall policy: default deny stance, inter-VLAN rules, and logging strategy.
- Remote access: VPN design, authentication approach, and least-privilege profiles.
- Observability: syslog/TLS export targets, log categories enabled, and retention considerations.
- Resilience: backup/restore process, config export hygiene, and change tracking.

Configuration examples will use sanitized placeholders and avoid storing secrets or private keys.
