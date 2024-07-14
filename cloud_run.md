# Cloud Run
 
Is a managed service and is the future of App Engine.

Managed compute platform which allows containers to be run via requests or events. Cloud Run is serverless. Cloud Run automatically scales your container out to handle the received requests, then scales in when demand decreases. You only pay for the CPU, Memory and Networking consumed during request handling.

- Pay per use
- Up to 1000 container instances by default.
- Can use with IAP.
- Manage identities that can acces service or allow unauth access
- Containers isolated to gVisor sandbox.
- Service is the main abstraction. It is located in a region and can be across zones.
- Revision is a deployment of a service, it consists of a specific image and configuration.
- Container instances run revisions and autoscale based on load. 
- Concurrency, up to 80 (default) simultaneous requests (1-1000 min-max). Cloud Functions can only have concurrency of 1.
- 
