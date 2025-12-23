# Architecture

High-level view of the lab showing how network segments, security controls, and observability fit together.

## Component Map
- Hardware/Proxmox host: compute, storage, and virtual networking for the lab.
- pfSense VM: firewall, router, DHCP/DNS, VPN termination, and segmentation enforcement.
- Management jump host: controlled entry point for administering Proxmox, pfSense, and workloads.
- Docker node(s): application and utility containers, kept on internal networks.
- Splunk stack: Heavy Forwarder as the collection tier, index/search node(s) for analytics and dashboards.
- Cribl Stream: normalization, filtering, and routing of telemetry before it hits Splunk.

## Network Segmentation
```
Internet
   |
[ISP/Edge]
   |
[pfSense Firewall/Router]
 |-- MGMT (VLAN10) -> admin jump host, hypervisor management
 |-- LAB  (VLAN20) -> app/utility VMs and Docker node(s)
 |-- DMZ  (VLAN30) -> any externally exposed services or reverse proxy
 |-- VPN  (VLAN40) -> remote access termination, scoped to least privilege
```
Actual VLAN IDs and IP ranges will be finalized during the network phase; default deny is enforced between segments with explicit allows only.

## Data and Logging Flow
- pfSense exports syslog to Cribl, which normalizes and forwards to Splunk (via Heavy Forwarder to indexers).
- Docker hosts forward container logs either through a local Universal Forwarder or syslog into Cribl before Splunk.
- Platform metrics (hypervisor, nodes) are collected with forwarders and sent through the same pipeline for consistency.
- All flows prefer TLS where possible; unauthenticated protocols are limited to lab-only networks.

## Notes for Future Expansion
- Add identity-aware access (SSO) for Splunk and management portals.
- Introduce an archival destination (object storage) for long-term log retention.
- Consider a second pfSense or virtual switch for blue/green or lab vs. prod isolation.
