# sport-os-infra

[![CI](https://github.com/valentinmariusdynu-tech/sport-os-infra/actions/workflows/ci.yml/badge.svg)](https://github.com/valentinmariusdynu-tech/sport-os-infra/actions/workflows/ci.yml)

Terraform, Kubernetes, and CI/CD infrastructure for the Sport-OS platform.

## Stack
Terraform 1.x · Docker · Kubernetes · Helm 3 · GitHub Actions

## Structure
```
envs/
├── dev/          — development environment tfvars
├── staging/      — staging environment tfvars
└── prod/         — production environment tfvars
modules/          — reusable Terraform modules
charts/           — Helm charts per service
├── backend/
├── ai/
└── docs/
.github/
└── workflows/    — deploy pipelines per environment
```

## Quick Start
```bash
cd envs/dev
terraform init
terraform plan
terraform apply
```

## Dev Commands
```bash
terraform fmt -recursive          # format all .tf files
terraform validate                # validate current module
helm lint charts/<service>        # lint a chart
helm template charts/<service>    # dry-run render
```

## Related Repos
| Repo | Role |
|---|---|
| [sport-os-backend](https://github.com/valentinmariusdynu-tech/sport-os-backend) | Service deployed here |
| [sport-os-ai](https://github.com/valentinmariusdynu-tech/sport-os-ai) | ML service deployed here |
| [sport-os-docs](https://github.com/valentinmariusdynu-tech/sport-os-docs) | Docs site deployed here |
| [sport-os-docs](https://github.com/valentinmariusdynu-tech/sport-os-docs) | Documentation |
