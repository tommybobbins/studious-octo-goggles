#Apigee

# Apigee

Apigee is an API proxy which can be used to build/catalog/automate API queries. It supports REST, gRPC, SOAP and GraphQL. Proxy is an HTTP endpoint. Publish Proxy as a "Product". The developers can then register as an App developer and create and API key within Apigee.

It is used when Managing high value/volume of APIs with enterprise grade security and dev engagement.
For example it can add voice/payments/integrations/interconnected experiences. Proxy layer provides granular control over security, rate limiting, quotas, and analytics.

Producers need to be concerned about:

- Security
- Compatibility
- Measurements

Automatically creates a developer portal for 3rd parties to be able to discover your APIs.

Consumers need to be concerned about:

- Discoverability
- Availability

## Apigee Hybrid

Comprehensive API management for use  in any environment (on-prem or any cloud). It can be used when maintaining and processing API traffic within your own k8s cluster.
[Apigee API platform]-------[k8s----Apigee Runtime---k8s/]------[Backend services, App servers/Other services]

Apigee runtime in hybrid is made up of Cassandra/Redis/Ingress, Message processer, Watcher, Sync, Connect agent, Analytics

