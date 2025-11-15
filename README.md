<p align="center">
<img src="images/devops_checklist.svg" alt="DevOps Checklist"/>
</p>

## 🎯 Repository Purpose

Provide teams, organizations, and aspiring DevOps engineers a **comprehensive, modern guide** on DevOps best practices, tools, and workflows to build, secure, and deploy applications efficiently.

**Note**: These checklists are **opinionated** and based on industry experience with modern DevOps practices and DORA principles. They represent common patterns but are not universal truth. You should adapt them to your specific needs and context. Contributions, discussions, and improvements are more than welcome!

🚧 This repository is continuously evolving with DevOps best practices. Contributions and real-world insights are encouraged!

---

<center>
<table>
  <tr>
    <td align="center"><a href="#team"><img src="images/logos/team.svg" width="75px;" height="75px;" alt="Team" /><br /><b>Team</b></a></td>
    <td align="center"><a href="#git"><img src="images/logos/git.png" width="75px;" height="75px;" alt="Git" /><br /><b>Git</b></a></td>
    <td align="center"><a href="#cicd-tooling"><img src="images/logos/jenkins.png" width="75px;" height="75px;" alt="CI/CD" /><br /><b>CI/CD</b></a></td>
    <td align="center"><a href="#docker"><img src="images/logos/docker.png" width="75px;" height="75px;" alt="Docker" /><br /><b>Docker</b></a></td>
  </tr>
  <tr>
    <td align="center"><a href="#sonarqube"><img src="images/logos/sonarqube.svg" width="75px;" height="75px;" alt="SonarQube" /><br /><b>SonarQube</b></a></td>
    <td align="center"><a href="#application-security"><img src="images/logos/security.svg" width="75px;" height="75px;" alt="Security" /><br /><b>Security</b></a></td>
    <td align="center"><a href="#aws"><img src="images/logos/aws.svg" width="75px;" height="75px;" alt="AWS" /><br /><b>AWS</b></a></td>
    <td align="center"><a href="#terraform"><img src="images/logos/terraform.svg" width="75px;" height="75px;" alt="Terraform" /><br /><b>Terraform</b></a></td>
  </tr>
</table>
</center>
---

## Table of Contents

- [Team 👥](#team-)
  - [Responsibilities](#responsibilities)
  - [Skills](#skills)
  - [DevOps Culture](#devops-culture)
  - [Team Goals (DORA & SLOs)](#team-goals-dora--slos)
  - [For Aspiring DevOps Engineers](#for-aspiring-devops-engineers)
- [Production & Deployment](#production--deployment)
  - [CI/CD Strategy](#cicd-strategy)
  - [Deployment Models](#deployment-models)
  - [Release Management](#release-management)
- [Version Control - Git](#version-control---git)
  - [Repository Structure](#repository-structure)
  - [Branching Strategy](#branching-strategy)
  - [Git Workflow](#git-workflow)
  - [Security & Access](#security--access)
- [CI/CD Tooling](#cicd-tooling)
  - [Jenkins Setup](#jenkins-setup)
  - [Pipeline Best Practices](#pipeline-best-practices)
  - [Pipeline as Code (Jenkinsfile Example)](#pipeline-as-code-jenkinsfile-example)
  - [Modern CI/CD Alternatives](#modern-cicd-alternatives)
  - [Security & Credentials](#security--credentials)
  - [Plugins & Integrations](#plugins--integrations)
- [Code Quality - SonarQube](#code-quality---sonarqube)
  - [Setup & Configuration](#setup--configuration)
  - [Quality Gates](#quality-gates)
  - [Integration with CI/CD](#integration-with-cicd)
- [Containerization - Docker](#containerization---docker)
  - [Image Best Practices](#image-best-practices)
  - [Dockerfile Guidelines](#dockerfile-guidelines)
  - [Container Security](#container-security)
  - [Registry Management](#registry-management)
- [Artifact Management - Nexus](#artifact-management---nexus)
  - [Repository Setup](#repository-setup)
  - [Artifact Lifecycle](#artifact-lifecycle)
  - [Security & Access Control](#security--access-control)
- [Application Security (DevSecOps)](#application-security-devsecops)
  - [SAST - Static Application Security Testing](#sast---static-application-security-testing)
  - [SCA - Software Composition Analysis](#sca---software-composition-analysis)
  - [DAST - Dynamic Application Security Testing](#dast---dynamic-application-security-testing)
  - [Security in CI/CD (Shift-Left)](#security-in-cicd-shift-left)
  - [Vulnerability Management](#vulnerability-management)
- [Infrastructure as Code - Terraform](#infrastructure-as-code---terraform)
  - [Project Structure](#project-structure)
  - [Best Practices](#best-practices)
  - [State Management](#state-management)
  - [Modules & Reusability](#modules--reusability)
- [Cloud Platform - AWS](#cloud-platform---aws)
  - [Account Structure](#account-structure)
  - [Core Services](#core-services)
  - [Security & IAM](#security--iam)
  - [Cost Optimization](#cost-optimization)
  - [Networking](#networking)
- [Container Orchestration (ECS & Kubernetes/EKS)](#container-orchestration-ecs--kuberneteseks)
  - [Orchestrator Decision (ECS vs EKS)](#orchestrator-decision-ecs-vs-eks)
  - [AWS ECS Task Definitions](#aws-ecs-task-definitions)
  - [AWS ECS Service Configuration](#aws-ecs-service-configuration)
  - [Kubernetes/EKS Fundamentals](#kuberneteseks-fundamentals)
  - [Deployment Strategies](#deployment-strategies)
- [Monitoring & Observability (The Three Pillars)](#monitoring--observability-the-three-pillars)
  - [Three Pillars of Observability](#three-pillars-of-observability)
  - [Dashboards & Visualization (Grafana/CloudWatch)](#dashboards--visualization-grafanacloudwatch)
  - [Alerting & Incident Response](#alerting--incident-response)
- [Continuous Improvement](#continuous-improvement)
- [Getting Started Guide](#getting-started-guide)
- [Resources](#resources)
- [Contributing](#contributing)
- [Credits](#credits)
- [License](#license)

---

## Team 👥

### Responsibilities

- [ ] **Define Clear DevOps Responsibilities**
  - Core Responsibilities:
    - [ ] CI/CD pipeline development and maintenance
    - [ ] Infrastructure automation
    - [ ] Deployment orchestration
    - [ ] Monitoring and alerting setup
    - [ ] Security integration (DevSecOps)
    - [ ] Toolchain management
  - Collaborative Responsibilities:
    - [ ] Working with developers on deployment strategies
    - [ ] Collaborating with security teams on compliance
    - [ ] Supporting operations with infrastructure

- [ ] **Document Everything**
  - [ ] Team responsibilities clearly written
  - [ ] Runbooks for common operations
  - [ ] Incident response procedures
  - [ ] Onboarding documentation
  - [ ] Tool usage guides

### Skills

#### Must-Have Skills

- [ ] **Version Control (Git)**
  - [ ] Understanding of Git workflows (GitFlow, trunk-based)
  - [ ] Branching strategies and merge strategies
  - [ ] Git hooks and automation

- [ ] **CI/CD Fundamentals**
  - [ ] Pipeline design and implementation
  - [ ] Build automation
  - [ ] Deployment automation
  - [ ] Testing integration

- [ ] **Scripting & Automation**
  - [ ] Shell scripting (Bash/Zsh)
  - [ ] Python or another scripting language
  - [ ] Configuration management basics

- [ ] **Containerization**
  - [ ] Docker fundamentals
  - [ ] Container orchestration concepts
  - [ ] Image optimization

- [ ] **Cloud Platform Knowledge**
  - [ ] At least one cloud platform (AWS, Azure, GCP)
  - [ ] IaaS, PaaS, SaaS concepts
  - [ ] Cloud services for compute, storage, networking

- [ ] **Infrastructure as Code**
  - [ ] **Terraform**, CloudFormation, or similar
  - [ ] Configuration management (Ansible, Chef, Puppet)
  - [ ] Version control for infrastructure

- [ ] **Security Awareness**
  - [ ] Secure coding practices
  - [ ] Secrets management
  - [ ] Vulnerability scanning
  - [ ] Compliance basics (SOC2, HIPAA, etc.)

#### Good-to-Have Skills

- [ ] Programming languages (Go, Python, Java)
- [ ] **Kubernetes/EKS** for container orchestration
- [ ] Advanced networking concepts
- [ ] Database administration basics
- [ ] **Prometheus** and **Grafana** for monitoring and observability

### DevOps Culture

- [ ] **Break Down Silos**
  - [ ] Development and Operations work together
  - [ ] Shared responsibility for production
  - [ ] Cross-functional collaboration

- [ ] **Automation First Mindset**
  - [ ] Automate repetitive tasks
  - [ ] Infrastructure as Code everywhere
  - [ ] Self-service capabilities for developers

- [ ] **Continuous Improvement**
  - [ ] Regular retrospectives
  - [ ] Postmortem culture (blameless)
  - [ ] Metrics-driven improvements

- [ ] **Shift-Left Approach**
  - [ ] Security integrated early (DevSecOps)
  - [ ] Testing early in the pipeline
  - [ ] Quality checks from the start

### Team Goals (DORA & SLOs)

- [ ] **Define DORA Metrics (The Four Keys)**
  - [ ] **Deployment frequency** (How often you ship)
  - [ ] **Lead time for changes** (Time from commit to production)
  - [ ] **Mean time to recovery (MTTR)** (How fast you fix failures)
  - [ ] **Change failure rate (%)** (How often deployment fails)

- [ ] **Service Level Objectives (SLOs)**
  - [ ] Define **SLOs** for critical services (e.g., 99.9% uptime)
  - [ ] Define **SLIs** (Service Level Indicators) to measure SLOs (e.g., latency, error rate)
  - [ ] Pipeline execution time targets
  - [ ] Deployment success rates

- [ ] **Team Maturity Model**
  - [ ] Level 1: Manual Deployments - Moving to automation
  - [ ] Level 2: Automated CI/CD - Pipelines established
  - [ ] Level 3: Advanced Automation - Security integrated, monitoring
  - [ ] Level 4: Full DevSecOps - Shift-left, self-service, optimization

### For Aspiring DevOps Engineers

Welcome to DevOps! :wave: This checklist is your roadmap.

#### Learning Path (12 Months)

- [ ] **Month 1-2: Foundations**
  - [ ] Master Git basics (clone, commit, push, pull, branch, merge)
  - [ ] Learn Linux command line fundamentals
  - [ ] Start with Bash/Shell scripting
  - [ ] Understand CI/CD concepts

- [ ] **Month 3-4: CI/CD & Containers**
  - [ ] Set up Jenkins/GitHub Actions locally
  - [ ] Create your first pipeline
  - [ ] Learn Docker basics
  - [ ] Build and run containers
  - [ ] Push images to Docker Hub/ECR

- [ ] **Month 5-6: Cloud & IaC**
  - [ ] Get AWS free tier account
  - [ ] Learn EC2, S3, VPC basics
  - [ ] Start with Terraform
  - [ ] Provision simple infrastructure

- [ ] **Month 7-8: Security & Quality**
  - [ ] Integrate SonarQube in pipeline
  - [ ] Learn about SAST/DAST/SCA tools
  - [ ] Understand secrets management
  - [ ] Practice secure coding

- [ ] **Month 9-12: Advanced Topics**
  - [ ] Container orchestration (**ECS/Kubernetes**)
  - [ ] Advanced AWS services
  - [ ] Monitoring and logging (**Prometheus/Grafana**)
  - [ ] Build complete end-to-end projects

#### Portfolio Projects

Build these to showcase your skills:

- [ ] **Project 1: Simple CI/CD Pipeline**
  - [ ] Git repo → GitHub Actions/Jenkins → Build → Test → Deploy to server

- [ ] **Project 2: Dockerized Application**
  - [ ] Multi-container app with Docker Compose
  - [ ] Published to registry

- [ ] **Project 3: AWS Infrastructure with Terraform**
  - [ ] VPC, EC2, RDS provisioned with IaC
  - [ ] Documented and in version control

- [ ] **Project 4: Complete DevSecOps Pipeline**
  - [ ] Git → CI Tool → SonarQube/SAST → SCA → Docker Build → DAST → Deploy to ECS/EKS
  - [ ] Security scans integrated
  - [ ] Monitoring and alerts set up

#### Career Development

- [ ] **Resume & Portfolio**
  - [ ] GitHub profile with projects
  - [ ] LinkedIn profile optimized
  - [ ] Personal blog/documentation
  - [ ] Certifications (AWS, Docker, etc.)

- [ ] **Networking**
  - [ ] Join DevOps communities
  - [ ] Contribute to open source
  - [ ] Attend meetups/conferences
  - [ ] Follow industry leaders

---

## Production & Deployment

### CI/CD Strategy

- [ ] **Define Deployment Strategy**
  - [ ] What triggers deployments? (commits, tags, manual)
  - [ ] How often do you deploy? (continuous, daily, weekly)
  - [ ] Who can trigger production deployments?

- [ ] **Environments**
  - [ ] Development environment
  - [ ] Testing/QA environment
  - [ ] Staging environment (production-like)
  - [ ] Production environment
  - [ ] Proper isolation between environments

- [ ] **Pipeline Stages**
  - [ ] Source code checkout
  - [ ] Build & compile
  - [ ] Unit tests
  - [ ] Code quality checks (**SonarQube**)
  - [ ] Security scans (**SAST**)
  - [ ] Dependency scanning (**SCA**)
  - [ ] Container image build
  - [ ] Integration tests
  - [ ] Security scans (**DAST**)
  - [ ] Artifact storage (**Nexus**)
  - [ ] Deployment to environments
  - [ ] Post-deployment tests

### Deployment Models

- [ ] **Choose Deployment Strategy**
  - [ ] **Blue-Green Deployment**: Two identical environments; switch traffic between them; easy rollback.
  - [ ] **Canary Deployment**: Gradual rollout to subset of users; monitor metrics before full rollout.
  - [ ] **Rolling Deployment**: Update instances one by one; zero downtime.
  - [ ] Recreate (Not recommended for production)

### Release Management

- [ ] **Versioning Strategy**
  - [ ] **Semantic versioning** (MAJOR.MINOR.PATCH)
  - [ ] Git tags for releases
  - [ ] Changelog maintained

- [ ] **Rollback Capability**
  - [ ] Quick rollback procedure documented
  - [ ] Automated rollback triggers
  - [ ] Database migration rollback strategy

- [ ] **Release Communication**
  - [ ] Release notes published
  - [ ] Stakeholders notified
  - [ ] Deployment windows communicated

---

## Version Control - Git

### Repository Structure

- [ ] **Organization**
  - [ ] Separate repositories for services (microservices approach)
  - [ ] Monorepo vs Multi-repo decision made
  - [ ] Clear naming conventions

- [ ] **Repository Content**
  - [ ] Application source code
  - [ ] Infrastructure as Code files
  - [ ] CI/CD pipeline definitions
  - [ ] Documentation (README, CONTRIBUTING)
  - [ ] `.gitignore` properly configured

- [ ] **Forbidden Content**
  - [ ] **NO secrets**, passwords, API keys
  - [ ] NO large binary files (use Git LFS if needed)
  - [ ] NO compiled artifacts (use artifact repository)

### Branching Strategy

- [ ] **Choose a Strategy**
  - [ ] **GitFlow** (for scheduled releases)
  - [ ] **Trunk-Based Development** (TBD) (for continuous deployment)
  - [ ] **GitHub Flow** (simplified)

- [ ] **Branch Protection**
  - [ ] `main` branch protected
  - [ ] Require pull request reviews
  - [ ] Require status checks to pass
  - [ ] No force push allowed
  - [ ] Require signed commits (optional but recommended)

### Git Workflow

- [ ] **Commit Practices**
  - [ ] Clear, descriptive commit messages
  - [ ] **Conventional commits** (feat:, fix:, docs:, etc.)
  - [ ] Small, atomic commits
  - [ ] No "work in progress" commits in main

- [ ] **Pull Request Process**
  - [ ] Pull request template defined
  - [ ] Code review required (at least 1-2 reviewers)
  - [ ] CI checks must pass
  - [ ] Link to issue/ticket
  - [ ] Description of changes

- [ ] **Git Hooks**
  - [ ] Pre-commit hooks for linting/formatting checks
  - [ ] Pre-commit hooks for **secret scanning**
  - [ ] Pre-push hooks to run local tests

### Security & Access

- [ ] **Access Control**
  - [ ] Least privilege principle
  - [ ] Role-based access (read, write, admin)
  - [ ] Regular access audits

- [ ] **Security Scanning**
  - [ ] Git secrets scanning (detect leaked credentials with tools like **GitLeaks** or **TruffleHog**)
  - [ ] Dependency vulnerability scanning
  - [ ] Automated security alerts

- [ ] **Backup & Disaster Recovery**
  - [ ] Git server/platform backups
  - [ ] Disaster recovery plan documented

---

## CI/CD Tooling

The CI/CD tool is the heart of automation. While **Jenkins** is robust, consider cloud-native alternatives like **GitHub Actions** or **GitLab CI** for reduced operational overhead.

### Jenkins Setup

- [ ] **Installation**
  - [ ] Jenkins installed (Docker, package, or cloud)
  - [ ] Master-agent architecture considered
  - [ ] High availability setup (for production)

- [ ] **Backup Strategy**
  - [ ] Jenkins home directory backed up
  - [ ] **Configuration as Code (JCasC)** implemented
  - [ ] Regular backup schedule

### Pipeline Best Practices

- [ ] **Pipeline Structure**
  - [ ] **Declarative pipeline** preferred (easier to read)
  - [ ] Stages clearly defined
  - [ ] Parallel execution where possible
  - [ ] Proper error handling

- [ ] **Build Optimization**
  - [ ] Use **Docker agents** for consistent builds
  - [ ] Cache dependencies (Maven, npm, pip)
  - [ ] Incremental builds where possible

- [ ] **Pipeline Stages**
  - [ ] Checkout → Build → Unit Tests → **Code Quality (SonarQube)** → **Security Scan (SAST/SCA)** → Containerize → Publish (**Nexus/Registry**) → Deploy → Verify

### Pipeline as Code (Jenkinsfile Example)

```groovy
pipeline {
    agent {
        docker {
            image 'maven:3.8.1-jdk-11'
        }
    }
    
    environment {
        SONAR_TOKEN = credentials('sonar-token')
        DOCKER_REGISTRY = 'your-registry.com'
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        
        stage('Code Quality & SAST') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.token=${SONAR_TOKEN}'
                sh 'trivy fs --security-checks vuln .'
            }
        }
        
        stage('Dependency Scan (SCA)') {
            steps {
                sh 'snyk test --json > snyk_report.json' // Example SCA
            }
        }
        
        stage('Package') {
            steps {
                sh 'mvn package -DskipTests'
            }
        }
        
        stage('Docker Build') {
            steps {
                sh 'docker build -t ${DOCKER_REGISTRY}/myapp:${BUILD_NUMBER} .'
            }
        }
        
        stage('Push to Registry') {
            steps {
                sh 'docker push ${DOCKER_REGISTRY}/myapp:${BUILD_NUMBER}'
            }
        }
        
        stage('Deploy to Dev') {
            steps {
                // Deployment steps
                sh './deploy.sh dev ${BUILD_NUMBER}'
            }
        }
    }
    
    post {
        success {
            echo "Build ${BUILD_NUMBER} succeeded" // Replace with slackSend
        }
        failure {
            echo "Build ${BUILD_NUMBER} failed" // Replace with slackSend
        }
        always {
            cleanWs()
        }
    }
}
```

### Modern CI/CD Alternatives

  - [ ] **GitHub Actions / GitLab CI / Azure DevOps:** Leverage integrated runners and simple YAML definition files for modern pipelines.
      - [ ] Lower maintenance overhead (no master/agent scaling).
      - [ ] Tight integration with the source control platform.
      - [ ] Native support for containers and cloud platforms.

### Security & Credentials

  - [ ] **Credentials Management**

      - [ ] Use credentials management systems (Jenkins Credentials, Cloud Secrets Manager, or HashiCorp **Vault**).
      - [ ] **NO hardcoded secrets** in pipeline files.
      - [ ] Rotate credentials regularly.

  - [ ] **Access Control**

      - [ ] Role-based access control (RBAC)
      - [ ] Audit logs enabled

### Plugins & Integrations

  - [ ] **Essential Plugins**
      - [ ] Git, Docker, Pipeline, Credentials, SonarQube Scanner
      - [ ] Slack/Email notifications

-----

## Code Quality - SonarQube

### Setup & Configuration

  - [ ] **Installation**

      - [ ] SonarQube server installed (Docker is common)
      - [ ] Database configured (PostgreSQL recommended)

  - [ ] **Project Setup**

      - [ ] Projects created for each application
      - [ ] Quality profiles defined

### Quality Gates

  - [ ] **Define Quality Gates**

      - [ ] Code coverage threshold (e.g., \> 80%)
      - [ ] Bug and vulnerability limits (zero high/critical)
      - [ ] Code smell limits
      - [ ] Duplication percentage limits

  - [ ] **Enforcement**

      - [ ] Quality gate as pipeline stage
      - [ ] **Block deployment** if quality gate fails
      - [ ] Notify team of failures

### Integration with CI/CD

  - [ ] **PR Analysis**
      - [ ] Pull Request decoration enabled (comments on PRs with issues).
      - [ ] Block merge if quality gate fails.

-----

## Containerization - Docker

### Image Best Practices

  - [ ] **Base Images**

      - [ ] Use official, specific tags, not `latest`.
      - [ ] Use **minimal base images** (Alpine, distroless) for small size and minimal attack surface.
      - [ ] Keep base images updated.

  - [ ] **Image Size**

      - [ ] **Multi-stage builds** for smaller images.
      - [ ] Remove unnecessary files.
      - [ ] Use `.dockerignore` file.

### Dockerfile Guidelines

  - [ ] **Dockerfile Checklist**
      - [ ] Use multi-stage builds.
      - [ ] **Run as non-root user**.
      - [ ] Combine `RUN` commands to reduce layers.
      - [ ] Add health checks.
      - [ ] Use `ENV` for configuration.
      - [ ] Add labels for metadata.

### Container Security

  - [ ] **Security Scanning**

      - [ ] Scan images for vulnerabilities (e.g., **Trivy**, Snyk, Clair).
      - [ ] **Block deployment of vulnerable images**.

  - [ ] **Runtime Security**

      - [ ] Run containers as non-root.
      - [ ] Use **read-only file systems** where possible.
      - [ ] Limit resources (CPU, memory).

  - [ ] **Secrets Management**

      - [ ] NO secrets in images.
      - [ ] Mount secrets at runtime using orchestrator (ECS Secrets, Kubernetes Secrets, Vault).

### Registry Management

  - [ ] **Container Registry**

      - [ ] Choose registry (**ECR**, Docker Hub, GCR, Nexus).
      - [ ] Private registry for internal images.
      - [ ] Access control configured.

  - [ ] **Registry Operations**

      - [ ] Automated image builds.
      - [ ] Image promotion across environments.
      - [ ] Clean up old/unused images.

-----

## Artifact Management - Nexus

### Repository Setup

  - [ ] **Repository Types**

      - [ ] **Hosted**: Your internal artifacts.
      - [ ] **Proxy**: Cache external artifacts (Maven Central, npm, etc.).
      - [ ] **Group**: Combine multiple repositories.

  - [ ] **Repository Configuration**

      - [ ] Maven, npm, Docker registry, PyPI repository support.

### Artifact Lifecycle

  - [ ] **Versioning**

      - [ ] Snapshot vs Release repositories
      - [ ] Semantic versioning enforced
      - [ ] **Immutable releases** (can't overwrite)

  - [ ] **Promotion Strategy**

      - [ ] Workflow defined to promote artifacts from Dev → QA → Prod repositories.

  - [ ] **Cleanup Policies**

      - [ ] Remove old snapshots automatically.
      - [ ] Retain releases based on policy.

### Security & Access Control

  - [ ] **Authentication**

      - [ ] LDAP/Active Directory integration.
      - [ ] Token-based authentication for CI/CD.

  - [ ] **Authorization**

      - [ ] Role-based access control.
      - [ ] Read/write permissions per repository.

-----

## Application Security (DevSecOps)

### SAST - Static Application Security Testing

  - [ ] **SAST Implementation**

      - [ ] SAST integrated in CI/CD pipeline.
      - [ ] Scans run on every commit/PR.
      - [ ] Results block pipeline if critical issues found.

  - [ ] **What SAST Detects**

      - [ ] SQL injection vulnerabilities.
      - [ ] Cross-site scripting (XSS).
      - [ ] Hardcoded secrets/credentials.

### SCA - Software Composition Analysis

  - [ ] **SCA Implementation**
      - [ ] **Dependency Scanning** integrated in CI/CD pipeline (**Snyk, Dependabot, OWASP Dependency-Check**).
      - [ ] Check open-source libraries for known vulnerabilities and license compliance.
      - [ ] Maintain a software bill of materials (SBOM).

### DAST - Dynamic Application Security Testing

  - [ ] **DAST Implementation**

      - [ ] DAST runs in staging/pre-prod environment.
      - [ ] Automated scans after deployment.
      - [ ] **OWASP ZAP** (open-source) is a common tool choice.

  - [ ] **What DAST Detects**

      - [ ] Authentication/authorization flaws.
      - [ ] Configuration errors.
      - [ ] OWASP Top 10 vulnerabilities.

### Security in CI/CD (Shift-Left)

```
1. Code Commit
   ↓
2. SAST Scan (immediate feedback)
   ↓
3. Build & Unit Tests
   ↓
4. Dependency Scan (SCA)
   ↓
5. Container Image Scan (Trivy/Clair)
   ↓
6. Deploy to Staging
   ↓
7. DAST Scan (against running app)
   ↓
8. Deploy to Production
```

  - [ ] **Security Tools Integration**
      - [ ] **Secrets Scanning**: GitLeaks, TruffleHog (run against Git history).
      - [ ] **License Compliance**: Check license compatibility early.

### Vulnerability Management

  - [ ] **Vulnerability Tracking**

      - [ ] Centralized vulnerability dashboard.
      - [ ] Severity classification (Critical, High, Medium, Low).
      - [ ] **SLA for fixing vulnerabilities** defined and enforced.

  - [ ] **Security Policies**

      - [ ] No critical/high vulnerabilities allowed in production.
      - [ ] Regular security audits and penetration testing.

-----

## Infrastructure as Code - Terraform

### Project Structure

  - [ ] **Directory Layout**
      - [ ] **`environments/`**: Contains environment-specific configurations (`dev`, `staging`, `production`).
      - [ ] **`modules/`**: Contains reusable, well-tested code blocks (e.g., `vpc`, `ecs-cluster`).
      - [ ] **`backend.tf`**: Configuration for remote state.

### Best Practices

  - [ ] **Code Quality**

      - [ ] Use consistent naming conventions.
      - [ ] Add descriptions to all variables and outputs.
      - [ ] Use `terraform fmt` for formatting.
      - [ ] Run `tflint` for linting.

  - [ ] **Variables & Locals**

      - [ ] Don't hardcode values.
      - [ ] Use `locals` for computed values.
      - [ ] Use variable validation to enforce structure.

  - [ ] **Resource Management**

      - [ ] Use `for_each` instead of `count` for flexibility.
      - [ ] Use `prevent_destroy` for critical resources.
      - [ ] Tag all resources consistently.

### State Management

  - [ ] **Remote State**

      - [ ] Use remote backend (**S3 with DynamoDB locking** for AWS).
      - [ ] **NEVER commit state files to Git**.
      - [ ] Enable state locking and versioning.
      - [ ] Encrypt state at rest.

  - [ ] **Execution Control**

      - [ ] Implement a **CI/CD orchestration layer** (**Terraform Cloud/Enterprise**, **Atlantis**, or robust CI runners) to manage safe, concurrent `terraform apply` operations.
      - [ ] Separate state per environment.

### Modules & Reusability

  - [ ] **Module Design**

      - [ ] Keep modules small and focused.
      - [ ] Version modules with Git tags.
      - [ ] Document module inputs/outputs.

  - [ ] **CI/CD Integration**

      - [ ] `terraform plan` on pull requests.
      - [ ] Plan output commented on PRs (use **Infracost** for cost estimation).
      - [ ] `terraform apply` triggered on merge to main/protected branches.

-----

## Cloud Platform - AWS

### Account Structure

  - [ ] **Multi-Account Strategy**

      - [ ] Separate AWS accounts per environment (**Dev, Staging, Prod**).
      - [ ] Use **AWS Organizations** for governance and consolidated billing.
      - [ ] Implement **Service Control Policies (SCPs)**.

  - [ ] **Account Baseline**

      - [ ] **CloudTrail**, **GuardDuty**, and **Security Hub** enabled in all accounts.
      - [ ] Enable resource tagging for cost allocation.

### Core Services

  - [ ] **EC2**: Use Auto Scaling Groups, Launch Templates, and IMDSv2.
  - [ ] **Lambda**: Serverless functions, use environment variables, enable X-Ray tracing.
  - [ ] **S3**: Enable encryption, block public access by default, use lifecycle policies.
  - [ ] **RDS**: Use Multi-AZ for production, enable automated backups and encryption.

### Security & IAM

  - [ ] **IAM**

      - [ ] Enable MFA for all users.
      - [ ] Use **IAM roles**, not users, for applications (**least privilege** principle).
      - [ ] Rotate access keys regularly.

  - [ ] **Secrets Management**

      - [ ] Use **AWS Secrets Manager** or Parameter Store for runtime secrets.
      - [ ] Rotate secrets automatically.

### Cost Optimization

  - [ ] **Cost Management**

      - [ ] Set up billing alerts and use AWS Budgets.
      - [ ] Use Cost Explorer and Cost Anomaly Detection.

  - [ ] **Strategies**

      - [ ] Right-size instances.
      - [ ] Use **Reserved Instances** and **Savings Plans** for steady workloads.
      - [ ] Use **Spot Instances** for non-critical, flexible workloads.

-----

## Container Orchestration (ECS & Kubernetes/EKS)

### Orchestrator Decision (ECS vs EKS)

  - [ ] **When to use ECS (AWS-Native)**: Simpler needs, lower operational overhead, tighter AWS integration, Fargate preferred for serverless compute.
  - [ ] **When to use EKS (Kubernetes)**: Multi-cloud/hybrid needs, complex orchestration (Service Mesh), necessity of the Kubernetes ecosystem, team has existing K8s expertise.

### AWS ECS Task Definitions

  - [ ] **Checklist**
      - [ ] Use **Fargate** (serverless) or EC2 (for control).
      - [ ] Set appropriate CPU and memory.
      - [ ] Use **Task Roles** for AWS API access (least privilege).
      - [ ] Define **health checks**.
      - [ ] Use secrets from Secrets Manager/Parameter Store.
      - [ ] Configure logging to CloudWatch Logs.

### AWS ECS Service Configuration

  - [ ] **Setup**
      - [ ] Deploy to multiple Availability Zones.
      - [ ] Configure **Auto Scaling** (CPU, Memory, Request Count).
      - [ ] Set up **Load Balancer integration** (ALB/NLB).
      - [ ] Configure deployment circuit breaker.

### Kubernetes/EKS Fundamentals

  - [ ] **Core Resources**

      - [ ] Understand **Pods** (smallest deployable unit).
      - [ ] Understand **Deployments** (manages desired state of Pods).
      - [ ] Understand **Services** (stable internal access/load balancing).
      - [ ] Understand **ConfigMaps** and **Secrets**.

  - [ ] **Deployment Tooling**

      - [ ] Use **Helm** for package management and templating deployments.
      - [ ] Use K8s-native CD tools like **ArgoCD** or **Flux** (**GitOps** philosophy).

### Deployment Strategies

  - [ ] **Rolling Update** (default): Update instances one by one.
  - [ ] **Blue/Green Deployment**: Use CodeDeploy (for ECS) or K8s Service Selector switching (for EKS).
  - [ ] **Canary Deployment**: Deploy a small subset, monitor, and gradually shift traffic.

-----

## Monitoring & Observability (The Three Pillars)

### Three Pillars of Observability

  - [ ] **Logs**: CloudWatch Logs, ELK Stack, Splunk.
  - [ ] **Metrics**: **Prometheus** (time series data), CloudWatch Metrics.
  - [ ] **Traces**: **AWS X-Ray** or **Jaeger** (distributed tracing).

### Dashboards & Visualization (Grafana/CloudWatch)

  - [ ] **Visualization Tools**
      - [ ] Use **Grafana** to visualize data from Prometheus, CloudWatch, or other sources.
      - [ ] Centralized dashboards for key application and infrastructure health metrics.
      - [ ] Real-time monitoring enabled.

### Alerting & Incident Response

  - [ ] **Alerting Setup**

      - [ ] Define alerts based on SLOs and critical resource thresholds.
      - [ ] Integrate with notification channels (SNS, Slack, PagerDuty).
      - [ ] Use **Prometheus Alertmanager** for sophisticated grouping and routing.

  - [ ] **Runbooks**

      - [ ] On-call rotation defined.
      - [ ] **Runbooks** for common alerts are documented and accessible.

-----

## Continuous Improvement

  - [ ] **Metrics & KPIs**

      - [ ] Regularly review **DORA metrics** and **SLOs**.
      - [ ] Track pipeline execution time and cost.

  - [ ] **Retrospectives**

      - [ ] Regular team retrospectives.
      - [ ] **Blameless postmortems** to document lessons learned.

  - [ ] **Training & Development**

      - [ ] Regular cross-training sessions.
      - [ ] Continuous learning culture fostered.

-----

## Getting Started Guide

### For New Teams

1.  **Week 1-2: Foundation** (Git, AWS Accounts, IAM/Security Baseline).
2.  **Week 3-4: CI/CD Foundation** (Choose and implement CI Tool, Docker basics, first pipeline).
3.  **Week 5-6: Quality & Security** (Integrate SonarQube, SAST/SCA, set up Nexus).
4.  **Week 7-8: Infrastructure** (Terraform basics, provision VPC/Network).
5.  **Week 9-10: Container Orchestration** (Set up ECS/EKS, configure load balancing).
6.  **Week 11-12: Advanced Topics** (Implement Observability, Auto-scaling, Blue/Green deployment).

### For Individuals Learning DevOps

  - **Month 1**: Git + Linux + Bash scripting
  - **Month 2**: CI/CD (Jenkins/Actions) + Docker basics
  - **Month 3**: AWS fundamentals + Terraform
  - **Month 4**: Build end-to-end project
  - **Month 5-6**: Advanced topics (K8s/Prometheus) + portfolio projects

-----

## Resources

### Official Documentation

  - [Git Documentation](https://git-scm.com/doc)
  - [Jenkins Documentation](https://www.jenkins.io/doc/)
  - [Docker Documentation](https://docs.docker.com/)
  - [Terraform Documentation](https://www.terraform.io/docs)
  - [AWS Documentation](https://docs.aws.amazon.com/)
  - [Kubernetes Documentation](https://kubernetes.io/docs/)

### Learning Platforms

  - [A Cloud Guru](https://acloudguru.com/)
  - [Udemy DevOps Courses](https://www.udemy.com/topic/devops/)

### Communities

  - [DevOps Subreddit](https://reddit.com/r/devops)
  - [CNCF Slack](https://slack.cncf.io/)

-----

## Contributing

Contributions are welcome\! Please:

1.  Fork the repository
2.  Create a feature branch
3.  Make your changes
4.  Submit a pull request

-----

## Credits

See [credits.md](credits.md) for image and logo attributions.

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

---

**Remember**: DevOps is a journey, not a destination. Start small, automate incrementally, and continuously improve! 🚀