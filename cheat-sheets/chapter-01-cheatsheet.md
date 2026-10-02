# AZ-900 Chapter 1 Cheat Sheet: Cloud Concepts & Shared Responsibility

## Shared Responsibility Model by Service Type

| Responsibility | IaaS (VMs) | PaaS (App Service, SQL DB) | SaaS (Office 365) |
|---|---|---|---|
| **Data & Information** | Customer | Customer | Customer |
| **Devices (endpoints)** | Customer | Customer | Customer |
| **Accounts & Identities** | Customer | Customer | Customer |
| **Applications** | Customer | Customer | Microsoft |
| **Network Controls** | Customer | Customer | Microsoft |
| **Operating System** | Customer | Microsoft | Microsoft |
| **Physical Hosts** | Microsoft | Microsoft | Microsoft |
| **Physical Network** | Microsoft | Microsoft | Microsoft |
| **Physical Datacenter** | Microsoft | Microsoft | Microsoft |

**Exam Rule:** Customer ALWAYS responsible for: Data, Identities, Endpoints (all service models)

**Exam Rule:** Microsoft ALWAYS responsible for: Physical datacenter, network, hosts (all service models)

---

## Cloud Deployment Models

| Model | Definition | Exam Scenarios |
|---|---|---|
| **Public Cloud** | Resources owned/operated by third-party provider, shared among multiple organizations | Cost optimization, global scale, no hardware management |
| **Private Cloud** | Resources used exclusively by single organization, can be on-premises or hosted | Strict compliance, full control, legacy app support |
| **Hybrid Cloud** | Combines on-premises (private) with public cloud, data/apps move between them | Keep data on-premises + use Azure services, gradual migration |
| **Multi-Cloud** | Using services from multiple public cloud providers (Azure + AWS) | Avoid vendor lock-in, use best services from each provider |

**Exam Tip:** "Integrate on-premises with Azure" = Hybrid. "Use Azure AND AWS" = Multi-cloud.

---

## CapEx vs OpEx

| Type | CapEx (Capital Expenditure) | OpEx (Operational Expenditure) |
|---|---|---|
| **Payment** | Large upfront cost | Ongoing, pay-as-you-go |
| **Example** | Buy servers ($500k), datacenter | Azure VMs ($X/hour), storage ($X/GB) |
| **Cloud Model** | Traditional on-premises | Consumption-based cloud |
| **Billing** | Depreciate over years | Monthly/hourly charges |
| **Scaling** | Slow (buy more hardware) | Instant (provision resources on-demand) |

**Exam Scenario:** Unpredictable workload = OpEx (consumption-based). Predictable, constant workload over 3 years = CapEx can be cheaper.

---

## Consumption-Based Pricing Benefits

✅ **No upfront costs** - zero capital expenditure  
✅ **Pay for what you use** - if app stops, costs stop  
✅ **Scale on demand** - increase resources during peak, decrease during off-peak  
✅ **No wasted capacity** - don't pay for idle servers  

**Exam Trap:** Reserved Instances (1-year/3-year commitment) are NOT consumption-based - they're prepaid discounts.

---

## When to Choose Each Cloud Model (Exam Scenarios)

### Choose **Public Cloud** when:
- Need global scale quickly
- Want to eliminate hardware management
- Workload is unpredictable/variable
- Startup or new project

### Choose **Private Cloud** when:
- Government/regulatory requirements mandate on-premises
- Need complete control over hardware
- Legacy apps can't be refactored
- Data sovereignty laws require in-country hosting

### Choose **Hybrid Cloud** when:
- Gradual migration from on-premises to cloud
- Some data must stay on-premises (compliance)
- Seasonal workload bursting (on-premises + cloud overflow)
- Use Azure AI/ML services on on-premises data

---

## Key Exam Numbers & Facts

**Shared Responsibility:**
- IaaS: Customer manages ~50% (OS up)
- PaaS: Customer manages ~20% (app + data)
- SaaS: Customer manages ~5% (data + identities only)

**DDoS Protection:**
- DDoS Protection Basic: FREE, automatic on all Azure services
- DDoS Protection Standard: Paid, enhanced protection for VNets

**Exam Weight:** Cloud Concepts = 25-30% of AZ-900 exam

---

## Common Exam Traps

❌ **TRAP:** "Who patches OS in PaaS?" → Customer (WRONG)  
✅ **CORRECT:** Microsoft patches OS in PaaS automatically

❌ **TRAP:** "Network security is shared responsibility in all models" (WRONG)  
✅ **CORRECT:** Network controls are customer responsibility in IaaS/PaaS, Microsoft in SaaS

❌ **TRAP:** "Multi-cloud = Azure + on-premises" (WRONG)  
✅ **CORRECT:** Multi-cloud = multiple PUBLIC clouds. Azure + on-premises = Hybrid

❌ **TRAP:** "Reserved Instances = consumption-based pricing" (WRONG)  
✅ **CORRECT:** Reserved = prepaid commitment. Consumption = pay-as-you-go only

---

## Quick Decision Trees

**Need OS control?**  
→ YES = IaaS  
→ NO = PaaS or SaaS  

**Who patches the OS?**  
→ IaaS = Customer  
→ PaaS/SaaS = Microsoft  

**Cost model for variable traffic?**  
→ Consumption-based (OpEx)  

**Must keep data on-premises + use Azure?**  
→ Hybrid cloud
