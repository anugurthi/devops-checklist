# DevSecOps Checklist

## SAST
- Integrated in CI/CD; runs on every commit/PR; blocks on critical issues

## SCA
- Dependency scanning (Snyk, Dependabot, OWASP Dependency-Check)
- Maintain SBOM

## DAST
- Automated staging scans (OWASP ZAP)

## Shift-Left Security Flow
Code Commit → SAST → Build/Test → SCA → Image Scan → Deploy to Staging → DAST → Prod Deploy

## Secrets Scanning
- GitLeaks/TruffleHog scan full history (all branches & tags)
- Pre-commit hooks prevent secret introduction
- Weekly/monthly historical scans

## Ephemerality of Runners ⚠️ REQUIRED
- All CI/CD build agents/runners must be **ephemeral** (containers, Kubernetes pods, short-lived VMs) and destroyed after each job to mitigate credential persistence and supply chain risk.

## Secrets Management & Rotation ⚠️ REQUIRED
- Immediate revocation & rotation (<15 min SLA) upon detection
- History cleanup (git-filter-repo/BFG) + follow-up verification
- Mandatory pre-commit secret hooks
- Rotation schedule ≤90 days; automated where possible

## Vulnerability Management
- Central dashboard; severity classification
- Defined remediation SLAs; zero critical/high in production

## Policy Enforcement
- OPA/Sentinel/tfsec/Checkov in pipeline stages

## License Compliance
- Early license scanning; block incompatible licenses

## Metrics
- Time-to-detect secrets
- Time-to-remediate vulnerabilities
- % builds passing security gates first attempt
