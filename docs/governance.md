# Governance & Policy as Code Checklist

## OPA / Gatekeeper
- Admission control deployed; Rego policies version-controlled
- Enforce resource limits, pod security, mandatory labels, registry restrictions
- Policy unit tests (conftest); audit → enforce progression

## Sentinel (Terraform)
- Policies before apply; tag enforcement; prevent public S3; encryption required
- Advisory vs mandatory levels documented; override procedure defined

## Cloud Compliance
- AWS Config, Azure Policy, GCP Org Policies enabled
- CIS benchmark & custom rules; automatic remediation (SSM / Functions)
- Compliance dashboards & non-compliant resource tracking

## CI/CD Policy Enforcement
- conftest/tfsec/Checkov integrated; policy failures block merge
- Reports attached to PRs; exception workflow with approvals

## Audit & Reporting
- Infrastructure change logs; API call trails; policy decision logs
- Automated compliance snapshots; executive summaries

## Framework Mapping
- SOC 2, PCI-DSS, HIPAA, GDPR, ISO 27001 mapped to technical controls

## Metrics
- Policy violation rate; time-to-remediate; % resources passing first scan
