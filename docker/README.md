# Docker

Manual-first learning plan for containerizing services inside the lab while keeping strong observability.

## Learning Plan
- Install Docker CE on a lab node and document the baseline configuration (users, storage, networking).
- Run foundational containers (e.g., nginx, busybox) using explicit commands to understand flags and defaults.
- Build a minimal custom image; manage tags, pushing/pulling from a private registry placeholder.
- Explore Docker networking (bridge, macvlan) and how it interacts with lab VLANs.
- Manage volumes and secrets carefully; store only sanitized examples in the repo.
- Configure logging drivers (json-file/syslog) and forward container logs into the Cribl/Splunk pipeline.
- Introduce Compose only after the manual workflows are comfortable; keep rollback steps handy.
- Review hardening: least-privilege users, image updates, and regular cleanup of unused images/volumes.

## Deliverables
- Documented commands, troubleshooting steps, and validation checks for each milestone.
- Notes on how container logging and networking integrate with pfSense policies.
