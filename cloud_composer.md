
# Cloud Composer

Managed Workflow Service based on Apache Airflow Service (cf to Argo Workflows/Step functions). It is a Pipeline orchestration for complex workflows. Executes workflows defined in DAGs (directed acyclic graphs).

## DAGs

- Workflow is collection of tasks with dependencies.
- DAGs are scripted in Python and Stored in Cloud Storage.
- Decision trees.
- A Task is a unit of work
- Operator is an action, transfer or sensor
- Hooks 3rd party services run before or after a task
- Plugins are (Hooks + Operator)

## Logs

- Workflow logs associated wih a single DAG Task
- Logs are available in web interface
- Log folder in associated cloud storage bucket
- Streaming logs will be passed through to the Log viewer for schedule, webserver, workers etc

## Architecture

Deployed in Environments, based on GKE. Tenant and Customer resources. 
Cloud Storage for staging workflow, plugins, logs and data dependencies
Redis is also deployed as the message broker.