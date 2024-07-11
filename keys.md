# Google Managed Keys

- Default
- Data encryption keys are stored near data chunks.
- Keys are stored in central key managed store.

# Customer Managed Keys

- Cloud KMS is hosted key management system.
- Customers generate and store keys in GCP.
- Used when customers want control over key generation and/or do not want to support key management infrastructure.
- Used for application level encryption.

# Custom Supplied Encryption Key

- Customer generate key and stores keys in self-managed infrastructure.
- Users want full control.
- Keys are passed to GCP via API when needed.