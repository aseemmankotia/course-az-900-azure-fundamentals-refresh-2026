# Azure Regions, Availability Zones, and Resource Organization Cheat Sheet

## Regions & Geography
| Concept | Definition | Exam Key Point |
|---------|------------|----------------|
| **Region** | Geographic area with ≥1 datacenter | Over 60 regions worldwide; select based on latency, compliance |
| **Geography** | Market boundary (e.g., Americas, Europe, Asia Pacific) | Data residency within geography; GDPR = Europe geography |
| **Region Pairs** | Two regions ≥300 miles apart | Automatic replication for disaster recovery; predetermined by Azure |
| **Availability Zones** | 1-3 physically separate datacenters in region | Protect against datacenter failure; 99.99% SLA for VMs |
| **Sovereign Regions** | Isolated clouds (Government, China) | Physical/logical isolation from public Azure |

## Availability Zones vs Region Pairs
| Feature | Availability Zones | Region Pairs |
|---------|-------------------|---------------|
| **Failure Scope** | Single datacenter | Entire region |
| **Distance** | Within same metro area | ≥300 miles apart |
| **SLA** | 99.99% for VMs | Disaster recovery (no specific SLA) |
| **Latency** | <2ms between zones | Higher (different geographies) |
| **Use Case** | High availability | Business continuity/disaster recovery |
| **Cost** | No cross-region charges | Cross-region data transfer fees |

## Resource Organization Hierarchy
```
Management Group (up to 6 levels deep)
└── Subscription (billing boundary)
    └── Resource Group (logical container)
        └── Resource (VM, Storage, etc.)
```

## Resource Groups: Critical Properties
| Property | Rule | Exam Trap |
|----------|------|------------|
| **Lifecycle** | Delete RG = delete ALL resources | Resources do NOT move to default group |
| **RBAC Scope** | Natural permission boundary | Common org pattern: separate RGs by team |
| **Cannot Nest** | No parent-child RG relationships | Management groups nest, RGs do NOT |
| **Location** | Metadata location only | Resources can be in ANY region |
| **Subscription Scope** | Exists in exactly ONE subscription | Cannot span multiple subscriptions |

## Subscriptions
| Aspect | Details |
|--------|----------|
| **Purpose** | Billing boundary, access control boundary |
| **Limits** | Separate quotas per subscription (e.g., 25,000 VMs per region) |
| **Use Cases** | Dev/Test/Prod separation, department billing, compliance isolation |
| **Relationship** | Belongs to ONE management group at a time |

## Management Groups
| Feature | Specification |
|---------|---------------|
| **Max Depth** | 6 levels (excluding root) = 7 total with root |
| **Purpose** | Apply policies/RBAC across multiple subscriptions |
| **Root** | Auto-created per Azure AD tenant |
| **Subscription** | Can be in only ONE management group |
| **Inheritance** | Policies flow DOWN the hierarchy |

## Common Exam Scenarios
**Scenario 1: GDPR Compliance + Disaster Recovery**
- ✅ Use region pairs within Europe (West Europe ↔ North Europe)
- ❌ Availability zones alone (no cross-region DR)

**Scenario 2: 99.99% SLA Required**
- ✅ Deploy across 3 availability zones in one region
- ❌ Single zone deployment (99.9% SLA only)

**Scenario 3: Deleted Resource Group**
- ✅ ALL resources permanently deleted
- ❌ Resources moved to default group (false)
- ❌ 30-day soft delete retention (false for general resources)

**Scenario 4: Policy Across 15 Subscriptions**
- ✅ Management group with policy inheritance
- ❌ Individual subscription policies (admin overhead)

**Scenario 5: Team-Based Access Control**
- ✅ Organize resources into RGs by team, assign RBAC at RG level
- ❌ Subscription-level RBAC for granular control (too broad)

## Numbers to Memorize
- **Availability Zones per Region**: Up to 3
- **Region Pair Distance**: ≥300 miles / 480 km
- **Management Group Depth**: 6 levels (excluding root)
- **VM SLA with Availability Zones**: 99.99%
- **VM SLA Single Instance (Premium SSD)**: 99.9%
- **Azure Regions**: 60+ globally
- **Sovereign Clouds**: 3 (Government, China, Germany sunset)

## Quick Decision Tree
**Need high availability?** → Availability Zones (within region)
**Need disaster recovery?** → Region Pairs (cross-region)
**Need data sovereignty?** → Choose appropriate geography or sovereign cloud
**Need policy across subscriptions?** → Management Groups
**Need team-based permissions?** → Resource Groups with RBAC
**Need billing separation?** → Separate Subscriptions
