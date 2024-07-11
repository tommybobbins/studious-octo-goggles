# Data Loss Prevention

- Keep information private and confidential.
- Remove PII.

## Key Features

- Discover and classify PII.
- Automatically mask data, transform data into another form (e.g cryptographic hash).

## InfoTypes

- Pattern detectors
- Examples (DOB, Passwords, Auth tokens, SSN, Bank account numbers).
- Inspection job applies infotypes to a dataset.
- When a match occurs it returns a likelihood score, location.

## Risk Analysis Jobs

- Calculate probability data can be re-identified

## Best Practices

- Inventory and prioritize content to scan.
- Assign proper roles to DLP Service Accounts.
- Start by sampling data and using simple criteria.
- Schedule jobs using triggers.

## Reference Architecture

- Google provide a reference document. 
- Dataflow can kick of Cloud DLP which in turn uses Cloud KMS.
- De-identified data is moved to BigQuery.

## Compliance

HIPAA - Healhcare legislation
HITECH - transmission of healthcare data to business associates.
GDPR - EU citizens data.
