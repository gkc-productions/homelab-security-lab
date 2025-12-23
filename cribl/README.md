# Cribl

Cribl Stream will sit in front of Splunk to normalize, enrich, and route telemetry while keeping costs and noise low.

## Pipeline Goals
- Normalize pfSense, Docker, and system logs into consistent field names before indexing.
- Reduce noise with filtering, sampling, and suppression where appropriate.
- Mask or drop sensitive data before it leaves the source network.
- Provide routing controls for sending data to Splunk and future destinations (e.g., object storage).

## Routing Approach (Planned)
- pfSense syslog -> Cribl syslog input -> pipeline for normalization -> forward to Splunk Heavy Forwarder/indexer.
- Docker/app logs -> local forwarder or HTTP input -> pipeline with drop/keep rules -> route by index.
- System metrics -> forwarder input -> minimal enrichment -> forward with consistent metadata.

## Work in Progress
- Define reusable pipelines per source type and index naming conventions.
- Establish dashboards or reports to monitor drop rates, throughput, and anomalies.
- Keep configs exportable and versioned without embedding credentials or keys.
