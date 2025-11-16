# FinOps & Cloud Cost Optimization Checklist

## Tagging & Visibility ⚠️ REQUIRED
- Mandatory tag enforcement via Policy as Code (OPA/Sentinel) blocks untagged resource creation (environment, owner/team, project/app, cost-center, managed-by, expiry-date)
- AWS Tag Policies / Azure Policy / Terraform validations
- Automated tag compliance audits & remediation
- CUR / Cost Explorer / Azure / GCP cost dashboards configured; third-party (CloudHealth/Kubecost) integrated

## Cost Allocation & Anomalies
- Chargeback/showback reports; cost trend analysis; anomaly detection alerts

## Budget Management
- Budgets per account/project (50/80/100/120% thresholds); forecast alerts; monthly spend reviews

## Resource Right-Sizing
- Compute Optimizer, underutilized EC2 <40% CPU/memory flagged; downsizing & termination of idle instances
- Storage: S3 Intelligent-Tiering, lifecycle policies, EBS cleanup & snapshot pruning
- Databases: RDS/Aurora optimization & replica justification

## Kubernetes Cost Optimization
- Kubecost deployed; resource requests & limits on all pods ⚠️ REQUIRED and right-sized; cluster autoscaler tuned; spot nodes for tolerant workloads

## Commitment Discounts
- Reserved Instances / Savings Plans strategy; target 70–80% coverage steady workloads; quarterly utilization reviews
- Spot & Preemptible instances for batch/dev/test; graceful termination handling

## Cost Governance & Culture
- Engineering dashboards include cost KPIs; optimization backlog; recognition for savings
- Architecture reviews include cost impact; avoid over-engineering; minimize data transfer
- Waste elimination (idle/ zombie / duplicated resources) automated where possible

## Metrics
- Cost per customer/transaction; cloud cost as % revenue; error budget vs cost trade-offs; savings from optimization initiatives
