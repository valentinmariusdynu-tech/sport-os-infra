# sport-os-infra — Stack Conventions

## Stack
- Terraform 1.x for cloud provisioning
- Docker + docker-compose for local dev / CI builds
- Kubernetes + Helm 3 for production orchestration
- GitHub Actions for CI/CD pipelines

## Code Conventions
- Terraform modules in modules/, environments in envs/
- terraform fmt and terraform validate required before PR
- Secrets via env vars or Vault — never committed
- Helm charts in charts/

## Testing
- terraform plan diff review mandatory on infra PRs
- kubectl rollout status smoke check after every deploy

## Git
- Conventional commits (feat:, fix:, infra:)
- Infra PRs require manual approval gate before apply
- Remote state backend (S3 or Terraform Cloud)
