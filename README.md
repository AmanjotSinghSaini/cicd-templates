# CI/CD Templates

This repository contains the **core reusable workflow logic** used by wrapper workflows in other repositories to implement secure and standardized CI/CD pipelines.

## What's Inside

- `ci-template.yml` – Handles Docker build, security scans, testing, ECR push, and notifications (CI).
- `cd-template.yml` – Manages EKS deployments with image substitution, rollout validation, and ECR cleanup (CD).

## How to Use

These templates are meant to be **called using `workflow_call`** from GitHub Actions wrappers like `ci-wrapper.yml` and `cd-wrapper.yml`.

```yaml
jobs:
  build:
    uses: AmanjotSinghSaini/cicd-templates/.github/workflows/ci-template.yml@main
