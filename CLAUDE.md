# CLAUDE.md — sport-os-infra

## Purpose
Terraform, Kubernetes, Helm, and GitHub Actions infrastructure for all Sport-OS services.

## Stack
- Terraform 1.x (resource provisioning)
- Kubernetes + Helm 3 (workload deployment)
- Docker (container builds)
- GitHub Actions (CI/CD pipelines per environment)

## Key Directories
- `envs/{dev,staging,prod}/` — per-environment Terraform root modules
- `modules/` — reusable Terraform modules (network, database, cache)
- `charts/` — Helm charts for backend, ai, docs services
- `.github/workflows/` — deploy pipelines per environment

## Dev Commands
```bash
terraform fmt -recursive
terraform validate
helm lint charts/<service>
helm template charts/<service> --debug
```

## Conventions
- Remote state in S3/GCS; never commit `.tfstate` to git
- Pin Terraform provider versions in `versions.tf`
- One Helm chart per service; values overridden per environment
- Production deploys require manual approval via GitHub Actions environment

## Related Repos
- [sport-os-backend](https://github.com/valentinmariusdynu-tech/sport-os-backend) — service image + config
- [sport-os-ai](https://github.com/valentinmariusdynu-tech/sport-os-ai) — ML service image + config
