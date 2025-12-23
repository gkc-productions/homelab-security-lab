# Roadmap

A phased plan to build the lab manually, validate each layer, and only then introduce automation.

## Phase 0: Foundation
- Confirm hardware layout, Proxmox install plan, and baseline security on the host.
- Define naming conventions, IP scheme placeholders, and repository structure.
- Set documentation standards and establish a simple change log.

## Phase 1: Network (pfSense)
- Deploy pfSense on Proxmox with discrete interfaces for mgmt, lab, dmz, and vpn segments.
- Stand up DHCP/DNS, NAT, and baseline firewall rules with default deny between VLANs.
- Enable logging exports (syslog/TLS if available) and backup the pfSense config.

## Phase 2: Docker
- Install Docker on a lab node; run initial containers manually (no Compose yet).
- Explore container networking, volumes, and image hardening; document cleanup/rollback steps.
- Configure container logging to feed a forwarder or syslog for later ingestion.

## Phase 3: Splunk
- Stand up a Heavy Forwarder for collection and parsing; deploy initial index/search node(s).
- Define index strategy, retention placeholders, and data source onboarding steps.
- Onboard pfSense and Docker logs via forwarders; validate ingestion and basic dashboards.

## Phase 4: Cribl
- Deploy Cribl Stream to sit in front of Splunk inputs.
- Build pipelines for pfSense, Docker, and system logs: normalize fields, drop noise, and route by index.
- Add controls for masking sensitive fields and measuring drop/throughput rates.

## Phase 5: AI Assist
- Experiment with AI-assisted triage, detection tuning, and documentation summarization.
- Keep models/tools air-gapped from secrets; use synthetic or sanitized datasets.
- Capture workflows that add real value before integrating them permanently.

## Phase 6: Automation
- Convert proven manual steps into scripts or playbooks (e.g., Ansible, Terraform, or shell).
- Add CI-style checks for linting, formatting, and basic validation where practical.
- Formalize backup/restore and disaster recovery drills using the documented playbooks.
