# Git Checklist

## Repository Structure
- Separate repos per service (or deliberate monorepo decision)
- Source code + IaC + CI definitions + docs
- `.gitignore` tuned; no secrets, large binaries, or build artifacts

## Branching Strategy
- Choose: GitFlow / Trunk-Based / GitHub Flow
- Protect `main`; require reviews & status checks; disallow force push; optionally signed commits

## Workflow & Commits
- Conventional commits; atomic changes; clear messages
- Pull request template; linked issues; passing CI; descriptive diffs

## Hooks & Automation
- Pre-commit: linting, formatting, secret scanning
- Pre-push: run tests

## Security & Access
- Least privilege & role-based permissions
- Regular access audits
- Git secrets scanning (GitLeaks / TruffleHog) across full history
- Dependency vulnerability alerts enabled

## Backup & DR
- Platform backups & documented recovery plan

## Recommended Practices
- Enforce branch naming conventions (`feat/`, `fix/`, etc.)
- Auto-close stale branches
- Use CODEOWNERS for mandatory reviewers
