# Splunk

This folder captures the logging and analytics design for the lab, with an emphasis on forwarder strategy and topology clarity.

## Universal Forwarder (UF) vs Heavy Forwarder (HF)
- **Universal Forwarder**: lightweight agent for log collection; forwards raw/ minimally parsed data; minimal CPU/RAM footprint; ideal for endpoints and Docker hosts.
- **Heavy Forwarder**: full Splunk instance capable of parsing, routing, filtering, and securing data at the edge; used as a collection tier and protocol bridge (e.g., syslog to Splunk).

## Planned Topology
- One Heavy Forwarder in a controlled network (preferably DMZ) receiving syslog from pfSense and data from UFs.
- Initial single index/search node, with room to expand to a dedicated search head and indexer pair later.
- UFs installed on Linux nodes and Docker hosts to ship logs to the HF; pfSense sends syslog directly until UF support is viable.
- Index strategy and retention policies defined per data source (pfSense, docker/app, system metrics) with placeholders for exact names.
- TLS for forwarder-to-HF and HF-to-indexer links where supported; local firewall rules restrict who can send data.

## Next Steps
- Define initial indexes, sourcetypes, and onboardings for pfSense and Docker.
- Capture HF app/add-on requirements and scaling triggers.
- Document validation queries and health checks for ingest, parsing, and licensing.
