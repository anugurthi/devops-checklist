# AWS Cloud Platform Checklist

## Account Structure
- Multi-account (dev/staging/prod) via AWS Organizations
- SCPs for guardrails; consolidated billing

## Baseline Security
- CloudTrail, GuardDuty, Security Hub enabled in all accounts
- Centralized logging & tagging standards

## Core Services
- EC2: ASGs, Launch Templates, IMDSv2
- Lambda: environment variables, X-Ray tracing
- S3: encryption, block public access, lifecycle policies
- RDS: Multi-AZ, automated backups & encryption

## IAM
- MFA for all users; role-based access; no long-lived user keys
- Access key rotation; least privilege policies

## Secrets Management
- AWS Secrets Manager / Parameter Store; automatic rotation

## Cost Optimization
- Budgets & Cost Explorer reports
- Anomaly detection enabled
- Right-sizing & Reserved Instances/Savings Plans strategy
- Spot for stateless & fault-tolerant workloads

## Networking
- VPC design (subnets: public/private); security groups least privilege
- NACLs for coarse filtering; flow logs enabled

## Governance
- AWS Config rules + remediation
- Tag policies (environment, owner, cost-center) enforced

## Metrics
- Cost per account trend
- Security findings open > SLA
- % tagged resources compliance
