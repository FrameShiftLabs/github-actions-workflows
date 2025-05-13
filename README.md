## Reusuable Workflows

This repository contains Github Actions workflows that can be reused across repositories.

### Required Values
1. project_name - Project Name defined via env variable
2. node_version - Node.js Version

Example:
```
env:
  PROJECT_NAME: app-utility-functions
  NODE_VERSION: 20.11.0

```

### Variables
1. APPROVERS - Comma separated list of email addresses to approve the build to production (Set this at the organization/project level).
2. RESOURCE_GROUP - Azure Resource group to deploy changes from staging to production (Set this at the organization/project level).

### Secrets

#### Organization Level (Service Principal)
1. AZURE_CLIENT_ID 
2. AZURE_TENANT_ID
3. AZURE_SUBSCRIPTION_ID

#### Project Level (Azure App Service/Function App)
1. AZURE_PUBLISH_PROFILE