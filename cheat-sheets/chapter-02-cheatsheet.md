# Cloud Benefits Cheat Sheet - AZ-900 Exam

## High Availability - SLA Percentages (HEAVILY TESTED)

| Configuration | SLA | Downtime/Month | Downtime/Year | Requirements |
|--------------|-----|----------------|---------------|-------------|
| Single VM (Premium SSD) | 99.9% | 43.2 min | 8.76 hours | All disks Premium/Ultra |
| Availability Set | 99.95% | 21.6 min | 4.38 hours | 2+ VMs, 2+ fault domains |
| Availability Zones | 99.99% | 4.32 min | 52.56 min | 2+ VMs across zones |
| Multi-region | 99.99%+ | <4.32 min | <52.56 min | Active-active/passive |

**Exam Trap**: Single VM with Standard storage = NO SLA. Must use Premium SSD/Ultra Disk.

## Scaling Types (HEAVILY TESTED)

| Type | Direction | Description | Example | Limits |
|------|-----------|-------------|---------|--------|
| Vertical | Up/Down | Increase/decrease resources of single instance | 4 vCPU → 8 vCPU | VM size limits |
| Horizontal | Out/In | Add/remove instances | 2 VMs → 10 VMs | Nearly unlimited |
| Elastic | Both | AUTOMATIC scale out AND in based on demand | Auto-add VMs at 80% CPU | Requires autoscale rules |

**Exam Keywords**: "Automatic" + "reduces when not needed" = Elasticity. "More instances" = Horizontal. "Bigger VM" = Vertical.

## Reliability & Fault Tolerance

| Concept | Definition | Azure Tools | Exam Focus |
|---------|------------|-------------|------------|
| Fault Tolerance | Continue during failure | Availability Sets/Zones | Zero downtime |
| Disaster Recovery | Restore after major failure | ASR, Geo-replication | RTO/RPO acceptable |
| Redundancy | Multiple copies | LRS, ZRS, GRS storage | Data durability |

**RTO** = Recovery Time Objective (max downtime)  
**RPO** = Recovery Point Objective (max data loss)  
**Lower RTO/RPO = Higher cost**

## Predictability

**Performance Predictability**:
- Autoscaling maintains consistent performance
- Load balancing distributes traffic
- SLAs guarantee uptime levels

**Cost Predictability**:
- Azure Cost Management forecasts spending
- Reserved Instances (1-3 year commit = lower cost)
- Spending limits prevent overages
- Azure Pricing Calculator estimates costs

**Exam Tip**: Predictability questions test BOTH performance consistency AND cost forecasting.

## Governance & Manageability

| Tool | Purpose | Exam Use Case |
|------|---------|---------------|
| Azure Policy | Enforce standards (tags, encryption) | "Require all resources to have tags" |
| RBAC | Control WHO can do WHAT | "Only admins can delete VMs" |
| Azure Blueprints | Package policies + resources | "Deploy compliant environment" |
| Management Groups | Organize subscriptions | "Apply policies across 50 subscriptions" |

**Management OF cloud** = Deploy, scale, monitor resources  
**Management IN cloud** = Use cloud-based tools (portal, CLI, APIs, mobile app)

## Key Exam Gotchas

1. **99.9% vs 99.99%**: Difference is ~39 minutes/month downtime - huge for mission-critical apps
2. **Scalability ≠ Elasticity**: Scalability = can scale. Elasticity = automatically scales down too.
3. **Availability Set ≠ Availability Zone**: Sets = racks in building (99.95%). Zones = separate buildings (99.99%).
4. **Single VM SLA**: Only with Premium/Ultra Disk - Standard storage = no SLA
5. **Vertical scaling limits**: Can't scale up forever - VM sizes have maximums. Horizontal is nearly unlimited.
6. **RBAC vs Policy**: User permissions = RBAC. Resource configuration rules = Policy.
7. **Fault tolerance costs**: Zero downtime is expensive - multi-region, active-active, premium services.

## Quick Calculations

**Monthly downtime from SLA**:  
30 days × 24 hours × 60 min × (100% - SLA%) = downtime minutes

**Examples**:  
99.9% → 30 × 24 × 60 × 0.1% = 43.2 minutes  
99.99% → 30 × 24 × 60 × 0.01% = 4.32 minutes

**Exam saves time**: Memorize 99.9% = ~43 min, 99.99% = ~4 min monthly.
