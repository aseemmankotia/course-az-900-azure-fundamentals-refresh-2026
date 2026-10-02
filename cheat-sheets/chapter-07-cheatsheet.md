# Azure Cost Management & Pricing Cheat Sheet

## Pricing Tools Comparison

| Tool | Purpose | When to Use | Exam Scenario |
|------|---------|-------------|---------------|
| **Pricing Calculator** | Estimate NEW workload costs | Before deploying resources | "Estimate monthly cost for 3 VMs + SQL DB" |
| **TCO Calculator** | Compare on-prem vs Azure (3-5 years) | Migration ROI decisions | "Calculate 5-year savings moving datacenter to Azure" |
| **Cost Management + Billing** | Track actual spending | Monitor deployed resources | "See which department spent most last month" |
| **Azure Advisor** | Cost optimization recommendations | Reduce existing resource costs | "Find underutilized VMs to downsize" |

## Factors Affecting Azure Costs

1. **Resource Type**: VM SKU (D2s vs D4s), storage tier (Hot/Cool/Archive), database tier (Basic/Standard/Premium)
2. **Consumption**: Hours running, GB stored, transactions, data transfer
3. **Region**: West US often cheaper than North Europe/Japan East for same resources
4. **Commitment**: Pay-as-you-go (full price) vs Reserved Instances (discounted)

## Pricing Models Comparison

| Model | Discount | Commitment | Best For | Exam Trap |
|-------|----------|------------|----------|----------|
| **Pay-as-you-go** | 0% | None | Variable/dev workloads | Most expensive per hour |
| **Reserved (1-year)** | ~40% | 1 year | Consistent workloads | Can't change VM size easily |
| **Reserved (3-year)** | ~72% | 3 years | Predictable 24/7 production | Highest commitment risk |
| **Spot VMs** | ~90% | None | Interruptible batch jobs | Can evict with 30s notice |
| **Hybrid Benefit** | ~40% | Bring own license | Existing Windows/SQL licenses | Different from Reservations |

## Cost Management Strategies

### Tags for Cost Allocation
- **Purpose**: Filter and group costs by department, project, environment
- **Example**: Tag = "Department: Finance" → filter Cost Management by tag
- **Exam tip**: Tags are recommended for chargebacks, not separate subscriptions

### Budgets and Alerts
- **What**: Set spending limit (e.g., $10K/month) with alerts at 80%, 100%, 120%
- **Important**: Alerts only — does NOT stop resource creation
- **To enforce**: Combine with Azure Policy or automation

### Right-Sizing
- **What**: Downsize VMs based on actual utilization
- **Trigger**: Azure Advisor flags VMs with <10% CPU over 7 days
- **Savings**: ~50% when downsizing (e.g., D4s → D2s)

### Auto-Shutdown
- **Use case**: Dev/test VMs stopped nights/weekends
- **Savings**: ~65% reduction for 9am-5pm weekday usage
- **Never use for**: Production 24/7 workloads

### Storage Tier Selection

| Tier | Access Frequency | Cost | Retrieval Time | Minimum Duration |
|------|------------------|------|----------------|------------------|
| **Hot** | Daily/frequent | Highest | Instant | None |
| **Cool** | Monthly/infrequent | 50% cheaper storage | Instant | 30 days |
| **Archive** | Yearly/rarely | 90% cheaper storage | Hours (rehydrate) | 180 days |

**Exam rule**: <30 days/year access → Archive; <1/month → Cool; else → Hot

## Key Numbers for Exam

- **Spot VM discount**: Up to 90%
- **1-year RI discount**: ~40%
- **3-year RI discount**: Up to 72%
- **Hybrid Benefit savings**: Up to 40%
- **Cool tier minimum**: 30 days
- **Archive tier minimum**: 180 days
- **Spot VM eviction notice**: 30 seconds

## Common Exam Scenarios

**Scenario: Migration decision, compare on-prem vs Azure over 5 years**  
→ **TCO Calculator**

**Scenario: Estimate monthly cost for new app (3 VMs + storage + SQL)**  
→ **Pricing Calculator**

**Scenario: Track department spending for chargebacks**  
→ **Tags + Cost Management filtering**

**Scenario: Batch job runs 3 hours/day, can tolerate interruptions**  
→ **Spot VMs** (90% discount)

**Scenario: Production e-commerce site, runs 24/7 year-round**  
→ **3-year Reserved Instances** (72% savings)

**Scenario: Prevent spending over $15K/month**  
→ **Cost Management budget with alerts** (alerts only, not enforcement)

**Scenario: VMs show 12% CPU utilization consistently**  
→ **Right-sizing** (downsize VM SKU)

## Heavily Tested Concepts

1. **Pricing Calculator vs TCO Calculator use cases** — know when to use each
2. **Region affects pricing** — same VM costs more in some regions
3. **Spot VMs = interruptible only** — never for production requiring uptime
4. **Tags = cost allocation method** — not separate subscriptions
5. **Budgets send alerts** — don't enforce spending limits automatically
6. **Reserved Instances require commitment** — locked to region/VM size/term
