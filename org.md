# studious-octo-goggles
Google Cloud Certified Professional Cloud Architect Study Notes


## Entity Types

|Entity|Notes|
|---|---|
|Organization|Root level structure, automatically created. Google Workspace Super Admins are granted the ability to create IAM roles.|
|Folders|Logically arrange Projects into Folders (Nested OU equivalent in AWS)|
|Projects|Projects can exist inside Folders or not|
|Resources|GCP Resouces exist inside a Project|

Billing accounts have a payment profile associated with them in a single currency. A Project and it's service level resources are linked to one Cloud Billing Account at a time. A single billing account can be responsible for multiple Projects.
