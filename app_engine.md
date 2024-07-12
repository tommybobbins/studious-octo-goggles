# App Engine

Old service - platform as a service. Serverless managed service. Superceded by Cloud Run.
Suited to run microservices.
Originally limited to language specific runtimes but flexible allows any containers to run.

## Standard

- Pre-configured containers.
- Applications run in a secure sandbox.
- Autoscales, instances start in seconds.
- Pricing is based on instance hours.
- Python, Java, NodeJS, PHP, Ruby, Go.
- Minimum of 0 instances.

## Flexible

- BYOContainer containers.
- Any language.
- Access resources in the compute engine.
- Autoscales, instances start in minutes.
- Minimum of 1 instance.
- Pricing is based on vCPU, Memory and PD.


## Autoscaling

- Applications execute on App Engine Managed instances.
- Types of scaling - Automatic (based on metric), Basic (when receive requests), Manual (specified # of instances).
- configured in an app.yaml - target_cpu_utilization, target_throughput_utilization, max_concurrent_requests, max_pending_latency, min_pending_latency.

## Traffic Splitting

- Multi-versioned, feature branching
- IP based
- HTTP Cookies (GOOGAPPUID, value from 0-999)
- Random

## App Engine Cron service

App Engine cron service runs tasks at regular intervals or times.