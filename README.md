# Reusable GitHub Actions Workflows

Modern, pnpm-first CI/CD workflows for JavaScript/TypeScript projects.

## Features

- **pnpm by default** - Fast, efficient package management
- **Turborepo support** - Optimized for monorepos with smart caching
- **Angular support** - Dedicated workflows for Angular projects
- **Universal deployment** - Works with Azure App Service and Function Apps

## Available Workflows

### Build & Test
- `turborepo_build.yml` - Build Turborepo monorepos
- `angular_build.yml` - Build Angular applications
- `lint.yml` - Run linting and type checking

### Deployment
- `deploy_to_staging.yml` - Deploy to staging environment
- `deploy_to_production.yml` - Deploy to production (slot swap)

### Utilities
- `bundle_dependencies.yml` - Install and cache dependencies
- `checkout.yml` - Checkout code with caching
- `hold.yml` - Manual approval for production deployments

## Usage

```yaml
jobs:
  build:
    uses: FrameShiftLabs/github-actions-workflows/.github/workflows/turborepo_build.yml@main
    with:
      project_name: ${{ github.event.repository.name }}
      node_version: ${{ vars.NODE_VERSION }}
```

## Package Manager

These workflows use **pnpm exclusively**. If your project uses npm, pnpm will automatically create a `pnpm-lock.yaml` file when the workflow runs. No manual migration required.

## Configuration

### Variables
- `NODE_VERSION` - Node.js version to use
- `RESOURCE_GROUP` - Azure Resource group for deployments
- `APPROVERS` - Comma separated list of email addresses for production approval

### Secrets

For Azure deployments, configure these service principal secrets:
- `AZURE_CLIENT_ID` 
- `AZURE_TENANT_ID`
- `AZURE_SUBSCRIPTION_ID`