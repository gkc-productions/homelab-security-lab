# Homelab Security Lab

A portfolio-ready homelab documenting a manual-first build of a secure, segmented environment with enterprise-style observability.

## Project Purpose
- Simulate a realistic security stack for hands-on learning and storytelling.
- Practice designing, documenting, and defending a small-scale environment.
- Capture decisions and lessons in the open without exposing secrets.

## Goals
- Build each layer manually to understand the moving parts before automating.
- Enforce segmentation, least privilege, and strong logging from day one.
- Maintain clean documentation and playbooks for repeatability and review.
- Demonstrate ability to plan, operate, and iterate on a security-centric lab.

## Guiding Philosophy
- Manual-first, automate later when the workflow is proven.
- Observable by default: log, trace, and monitor every segment.
- Reproducible: document commands, configs, and rollback steps.
- Safe defaults: zero-trust mindset, minimal exposure, no secrets in the repo.

## Planned Stack
- Proxmox VE as the hypervisor hosting pfSense, Splunk, Cribl, and Docker nodes.
- pfSense for firewalling, DHCP/DNS, VPN, and segmentation across VLANs (mgmt, lab, dmz, vpn).
- Docker for app and utility workloads, starting with manual runs before Compose.
- Splunk: Universal Forwarders on endpoints, a Heavy Forwarder as a collection tier, and index/search components for analytics.
- Cribl Stream for shaping, filtering, and routing telemetry into Splunk and future destinations.
- GitHub + Markdown for change tracking, with playbooks for repeatable tasks.
- Optional AI helpers for triage, detection tuning, and documentation once the baseline is stable.

## Repository Layout
- `docs/` architecture overview and roadmap.
- `playbooks/` repeatable procedures and runbooks.
- `pfsense/` firewall and network segmentation notes.
- `docker/` container lab notes and experiments.
- `splunk/` logging and analytics design.
- `cribl/` data pipeline and routing design.

## Current Status
Planning and documentation in progress; infrastructure build starts after the roadmap is finalized.
