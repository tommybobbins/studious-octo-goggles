# Observability

- Latency. Time to complete a request. Distinguish between success and failure
- Traffic. Measure of demand on a system. HTTP requests/second, transactions/second.
- Errors. Rate of requests that fail. Explicit and Implicit.
- Saturation. Measure of capacity and constrained resources. Latency is often a good measure of saturation.

## Cloud Monitoring

- Collect Metrics from GCP, AWS and Hybrid.
- Dashboards and Visualizations.
- Alerting an anomaly reporting.
- Predefined and custom metrics.
- Monitoring agent.

Monitoring dashboard, Metric Explorer, History, Alerting, Uptime checks.

## Cloud Logging

- Centralized repository for ingesting logs.
- Managed service.
- fluentd is the underlying agent. 
- Retains logs for 30d. Export to cloud storage if longer required
- Stream logs to BigQuery
- Stream logs to Pub/Sub

Log viewer (kibana), metrics editor.
Log router is used to route logs to log syncs.

