# Contributing to DevOps Checklist

Thank you for your interest in contributing! 🎉

## How to Contribute

### Reporting Issues
- Use GitHub Issues to report bugs or suggest improvements
- Provide clear descriptions and examples
- Include your use case if applicable

### Submitting Changes

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make your changes**
   - Follow the existing format and structure
   - Use checkboxes `- [ ]` for actionable items
   - Include code examples where helpful
   - Add descriptions explaining the "why" behind practices

4. **Test your changes**
   - Preview the markdown rendering
   - Check all links work
   - Verify code examples are valid

5. **Commit your changes**
   ```bash
   git commit -m "feat: Add XYZ to the checklist"
   ```
   
6. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

7. **Submit a Pull Request**
   - Clearly describe what you've added/changed
   - Reference any related issues

## Guidelines

### Content Guidelines
- **Be practical**: Focus on actionable advice teams can implement
- **Be opinionated (but flexible)**: Share what works, but acknowledge alternatives
- **Be comprehensive**: Include both basics and advanced topics
- **Be modern**: Keep up with current DevOps practices (2024-2025)
- **Be clear**: Use simple language and good examples
- **Preserve existing content**: Don't delete good ideas - refine, reorganize, or extend them

### Formatting Guidelines

**Checklist Items:**
- Use checkboxes `- [ ]` for all actionable items
- Write in **imperative mood** (do this, configure that)
- Keep items **short and scannable** (one clear action per item)
- **Split long items**: If a bullet covers multiple ideas, break into sub-items
- Add **context in sub-bullets** when an item needs explanation

**Structure:**
- Use proper markdown heading hierarchy (##, ###, ####)
- Keep lines to ~80-100 characters for readability
- Use emojis sparingly: ⚠️ for critical, ⭐ for recommended, ✅ for benefits
- Include code examples in appropriate language blocks (```yaml, ```hcl, etc.)

### Style Guide

**Good Examples:**
```markdown
- [ ] **Terraform remote backend configured** ⚠️ **REQUIRED**
  - [ ] S3 bucket for state storage
  - [ ] DynamoDB table for state locking
  - [ ] Encryption at rest enabled
  - [ ] Versioning enabled for rollback
```

**Bad Examples:**
```markdown
- Configure Terraform to use remote state with S3 and DynamoDB and enable encryption and versioning for better security and collaboration (too long, multiple actions)
- State management (too vague, not actionable)
```

**Wording:**
- ✅ "Enable MFA for root account"
- ❌ "MFA should be enabled for root account"
- ✅ "Run security scans in CI/CD pipeline"
- ❌ "Security scans can be run in the pipeline"

### Where to Place New Items

| Topic | Section |
|-------|---------|
| Team practices, culture, roles | Team 👥 |
| Version control, branching, Git hooks | Version Control - Git |
| Jenkins, GitHub Actions, pipelines | CI/CD Tooling |
| Docker, containers, registries | Containerization - Docker |
| Code quality, testing, SonarQube | Code Quality - SonarQube |
| Artifacts, Nexus, Artifactory, ECR | Artifact Management |
| SAST, DAST, SCA, secrets scanning | Application Security |
| Terraform, IaC, state management | Infrastructure as Code |
| AWS, cloud services, IAM | Cloud Platform - AWS |
| Kubernetes, EKS, Helm, RBAC | Kubernetes Orchestration |
| Metrics, logs, traces (MLT stack) | Observability |
| OPA, Sentinel, compliance, policies | Governance & Policy as Code |
| Cost optimization, tagging, budgets | FinOps & Cloud Cost |

### Code Examples
- Test all code examples before submitting
- Use comments to explain complex parts
- Follow best practices for the language/tool
- Keep examples concise but complete

## Areas for Contribution

We especially welcome contributions in:
- Real-world examples and use cases
- Tool alternatives and comparisons
- Cost optimization strategies
- Security best practices
- Troubleshooting guides
- Links to quality resources
- Corrections and clarifications

## Questions?

Feel free to open an issue for discussion before making large changes.

Thank you for helping make DevOps practices more accessible! 🚀
