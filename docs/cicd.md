# CI/CD Tooling Checklist

## Strategy
- Prefer GitHub Actions / GitLab CI for new projects (managed, integrated)
- Jenkins with JCasC for complex enterprise customization

## Jenkins Setup (JCasC)
- All config in version-controlled YAML
- Docker-based installation & master-agent architecture
- HA for production; plugins managed declaratively

## Pipeline Best Practices
- Declarative pipelines; clear stage separation
- Parallelization; Docker agents; dependency caching
- Standard stage order: Checkout → Build → Unit Tests → Code Quality (SonarQube) → SAST/SCA → Containerize → Publish → Deploy → Verify

## Security & Credentials
- Centralized secret management (Vault/Secrets Manager)
- No hardcoded secrets; frequent rotation
- Least privilege for pipeline credentials
- Ephemeral build agents (containers or short-lived VMs) ⚠️ REQUIRED

## Modern CI/CD Alternatives
- GitHub Actions: marketplace, matrix builds, native integration
- GitLab CI: integrated DevSecOps scanning, built-in registry
- Benefits: no infra maintenance, strong DX, cloud-native, cost efficient

## Example (GitHub Actions)
```yaml
name: build-test
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-java@v3
        with:
          java-version: '11'
          distribution: 'temurin'
      - run: mvn -B clean test
      - name: Trivy
        uses: aquasecurity/trivy-action@master
        with:
          scan-type: 'fs'
          scan-ref: '.'
```

## Plugins & Integrations
- Core: Git, Docker, Credentials, SonarQube, Notifications

## Key Metrics
- Build duration
- Success/failure rate
- Mean time to fix broken builds
- Queue time / concurrency usage
