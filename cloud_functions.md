# Cloud Functions 

Serverless Compute service. Execute in response to events based on triggers.

- Lightweight APIs
- Lightweight ETL
- Webhooks
- Mobile Backends
- IoT

It can run for 60 minutes. HTTP and Service triggers. Set autoscaling - 0 is infinite number of concurrent functions.

## HTTP Trigger

- HTTP Auth/Unauth
- Declaritively split traffic.

## Service Triggers

- Pub/Sub.
- Cloud Storage
- Firestore
- Firebase
- Eventarc 
- (90 + event sources via cloud audit logs)

## Best Practices

- Write idempotent functions, same value if the same input.
- Send HTTP response in HTTP functions.
- Do not start background operations.
- Cleanup temporary files
- Do not manual exit (like sys.exit). Use return instead.
- Balance the use of imports with performances.
- Global variables to reuse variables. 
- Lazy initialization on global variables.
