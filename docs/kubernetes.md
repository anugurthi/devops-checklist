# Kubernetes Orchestration Checklist

## Cluster Management
- Managed services: EKS / GKE / AKS
- Multi-AZ nodes; upgrade strategy defined
- Node pools by workload type (compute/memory/GPU)
- Cluster autoscaler active; PDBs configured; network policies enforced

## Package Management
- Helm 3 for complex apps (versioned charts, env values files)
- Kustomize for lightweight overlays; avoid mixing both in one app

## RBAC & Security
- Least privilege service accounts; no default SA usage
- No cluster-admin for regular users
- Pod Security Standards enforced; non-root containers; dropped capabilities
- Network policies (default deny); mTLS via mesh if adopted
- External Secrets Operator for cloud secret managers
- Admission Control ⚠️ REQUIRED: OPA Gatekeeper or Kyverno enforces resource limits, approved registries, security contexts, mandatory labels

## Service Mesh
- Istio (feature-rich) or Linkerd (simplicity) or AWS App Mesh (AWS-native)
- mTLS enforced; traffic management (VirtualServices / TrafficSplit)
- Observability (Kiali / Linkerd Viz / Prometheus)

## Autoscaling & Resources
- HPA with CPU/memory + custom metrics
- VPA (recommendation mode initially)
- Cluster autoscaler tuned
- Resource requests & limits on all containers ⚠️ REQUIRED; quotas & limit ranges applied

## GitOps
- ArgoCD or Flux for pull-based sync & drift detection
- Apps defined as CRDs (Application / Kustomization / HelmRelease)
- Image automation for tag updates

## Deployment Strategies
- Rolling updates default
- Blue/Green & Canary supported
> **Progressive Delivery Note:** Use Istio, Linkerd, or Flagger for declarative traffic shifting and automated analysis in canary/blue-green rollouts instead of manual service selector switching.

## Security & Compliance
- Regular IAM Roles for Service Accounts (IRSA) usage (EKS)
- Private cluster endpoints & restricted API access

## Metrics & Monitoring
- Kube-state metrics, node exporter, custom app metrics
- Dashboards for capacity, saturation, error rates

## Cost Optimization
- Kubecost for visibility; right-size requests & node types; spot nodes for tolerant workloads
