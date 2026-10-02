# AZ-900 Exam Simulation and Test-Taking Strategy Cheat Sheet

## Exam Format Essentials

| Aspect | Details |
|--------|--------|
| **Duration** | 45 minutes active exam time |
| **Questions** | 40-60 questions |
| **Time per Question** | ~1 minute average |
| **Passing Score** | 700/1000 (70%) |
| **Question Types** | Multiple-choice, multiple-select, drag-and-drop, hot area |

## Exam Domain Weights

| Domain | Weight |
|--------|--------|
| Azure architecture and services | 35-40% |
| Management and governance | 30-35% |
| Governance and compliance tools | 10-15% |
| Managing and deploying resources | 10-15% |
| Cost management | 5-10% |

## Critical Keywords and What They Mean

| Keyword | Interpretation |
|---------|---------------|
| **BEST** | Multiple solutions work; choose optimal one |
| **MOST cost-effective** | Minimize costs while meeting requirements |
| **LEAST administrative effort** | Prefer managed services, automation |
| **highly available** | Look for Availability Zones (99.99% SLA) |
| **guaranteed uptime** | Need SLA-backed redundancy |
| **full control** | IaaS required (VMs, not PaaS) |
| **minimize complexity** | Choose simpler service (PaaS over IaaS) |

## Common Service Comparisons

### IaaS vs PaaS Boundaries

| Scenario | Choose IaaS | Choose PaaS |
|----------|------------|-------------|
| Need OS access | ✓ Virtual Machines | ✗ |
| Custom monitoring agents | ✓ VMs | ✗ |
| Quick web app deployment | ✗ | ✓ App Service |
| Minimize admin overhead | ✗ | ✓ Managed services |

### Calculators

| Tool | Use Case |
|------|----------|
| **Pricing Calculator** | Estimate Azure costs for new resources |
| **TCO Calculator** | Compare on-premises vs Azure migration costs |
| **Cost Management** | Track and analyze actual spending (post-deployment) |

### High Availability

| Feature | Protection | SLA |
|---------|-----------|-----|
| **Availability Zones** | Datacenter failures | 99.99% |
| **Availability Sets** | Rack failures only | 99.95% |
| **Single VM (Premium SSD)** | Hardware failures | 99.9% |
| **Multi-region** | Regional disasters | Highest (99.99%+) |

### Governance and Security

| Service | Purpose |
|---------|--------|
| **Azure Policy** | Enforce organizational standards, compliance |
| **Resource Locks** | Prevent deletion (CanNotDelete) or changes (ReadOnly) |
| **Azure RBAC** | Control who can access what resources |
| **Microsoft Defender for Cloud** | Unified security management, compliance dashboard |

## Pricing Models

| Model | Savings | Use Case |
|-------|---------|----------|
| **Pay-As-You-Go** | 0% (baseline) | Unpredictable workloads, testing |
| **Reserved Instances (1-year)** | Up to 40% | Predictable, steady workloads |
| **Reserved Instances (3-year)** | Up to 72% | Long-term, committed workloads |
| **Spot VMs** | Up to 90% | Interruptible, non-critical batch jobs |
| **Hybrid Benefit** | 40%+ on Windows/SQL | Existing licenses with Software Assurance |

## Elimination Strategy

1. **Read carefully**: Identify ALL requirements in question
2. **Eliminate obviously wrong**: Services that don't meet any requirement
3. **Check boundaries**: IaaS vs PaaS, regions vs zones, pricing models
4. **Look for traps**: Deprecated services, incomplete solutions
5. **Choose BEST**: If multiple work, pick most cost-effective/least effort

## Common Exam Traps

| Trap | What to Watch |
|------|---------------|
| **Spot VMs in production** | NEVER acceptable for critical workloads |
| **ReadOnly locks** | Block legitimate updates, not just deletions |
| **Over-provisioning Reserved Instances** | Don't reserve for peak capacity |
| **Confusing Pricing vs TCO Calculator** | Migration comparison = TCO |
| **Single region vs Availability Zones** | Zones = better SLA, same region |
| **Azure Policy vs Defender for Cloud** | Security posture = Defender |

## Time Management Tips

- **Flag difficult questions**: Return if time allows
- **Don't overthink**: First instinct often correct
- **Budget 30-40 seconds/question**: Leaves buffer for review
- **Case studies**: Read scenario once, answer all related questions
- **No penalty for guessing**: Answer every question
