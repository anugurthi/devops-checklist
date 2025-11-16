# Terraform Checklist

## Project Structure
- `environments/` per env (dev/staging/prod)
- `modules/` reusable components
- `backend.tf` remote state config

## Code Quality
- Naming conventions; descriptions for vars/outputs
- `terraform fmt`, `tflint` enforced
- Use `locals` for computed values

## State Management ⚠️ REQUIRED (Team)
- Remote backend with locking (S3+DynamoDB / Azure Blob / GCS / Terraform Cloud)
- Never commit state files; enforced via `.gitignore`
- Encryption at rest + in transit; versioning + logging
- MFA delete on production state buckets

## Backend Example (S3 + DynamoDB)
```hcl
terraform {
  backend "s3" {
    bucket         = "example-tf-state"
    key            = "app/prod/terraform.tfstate"
    region         = "us-east-1"
    dynamodb_table = "tf-state-lock"
    encrypt        = true
  }
}
```

## Security & Access
- Least privilege IAM policies
- Audit state access; enable bucket logging

## Execution Control
- CI orchestration (Terraform Cloud / Atlantis / GitHub Actions)
- Peer-reviewed `terraform plan` before apply
- Drift detection & automated cost estimation (Infracost)

## Modules
- Small, focused modules; semantic versioning
- Document inputs/outputs; examples provided

## Tagging & Governance
- Mandatory tags enforced via Sentinel/OPA

## Metrics
- Drift incidents/month
- Mean time to apply approved changes
- % modules reused vs duplicated
