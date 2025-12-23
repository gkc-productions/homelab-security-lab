# High-Level Architecture

## Overview
This homelab is designed as a layered system to simulate enterprise infrastructure
and security operations.

## Layers
1. Infrastructure Layer (Hardware + Proxmox)
2. Network & Security Layer (pfSense)
3. Platform Layer (Linux VMs, Docker)
4. Observability Layer (Splunk, Cribl)
5. Intelligence Layer (AI assistance)
6. Automation Layer (future)

## Network Segmentation (Planned)

Internet
   |
Router
   |
pfSense (VM)
   |
-----------------------------
|           |               |
MGMT_NET   LAB_NET        VPN_NET

## Notes
- All traffic is controlled through pfSense
- Network segmentation is used to simulate security groups
- Logging will be enabled at every layer
