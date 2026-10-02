## Chapter 1: Cloud Computing Fundamentals and Shared Responsibility — Practice Questions

**Q1.** A company is migrating their on-premises SQL Server databases to Azure. They want to maintain full control over the operating system, including patching schedules and custom configurations. Which Azure service model should they choose?

A) Azure SQL Database (PaaS)
B) SQL Server on Azure Virtual Machines (IaaS)
C) Azure SQL Managed Instance (PaaS)
D) Azure Cosmos DB (PaaS)

<details>
<summary>Answer</summary>

**Correct: B**

SQL Server on Azure VMs is IaaS - customer controls OS, patching, and all configurations. In IaaS, Microsoft manages physical infrastructure, customer manages everything from OS up including patching schedules.

**Why the others are wrong:**
- Azure SQL Database is PaaS - Microsoft manages OS and patching, customer cannot control OS-level configurations
- Azure SQL Managed Instance is PaaS - Microsoft manages OS, patching is automated, no OS-level access
- Azure Cosmos DB is PaaS - completely different database technology, no OS access, Microsoft manages all infrastructure

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A healthcare organization needs to store patient data with strict regulatory requirements that data must remain in their own datacenter, but they want to use Azure AI services for diagnostics processing. Which cloud deployment model fits this requirement?

A) Public cloud only
B) Hybrid cloud
C) Private cloud only
D) Community cloud

<details>
<summary>Answer</summary>

**Correct: B**

Hybrid cloud combines on-premises (private) infrastructure with public cloud services. Sensitive data stays on-premises while leveraging public cloud capabilities like Azure AI. This is the classic hybrid scenario.

**Why the others are wrong:**
- Public cloud only would move all data to Azure, violating the requirement to keep data in their datacenter
- Private cloud only would keep everything on-premises but wouldn't provide access to Azure AI services
- Community cloud is not a deployment model covered in AZ-900, and doesn't describe this Azure + on-premises scenario

</details>

---

**Q3.** A company deploys a web application using Azure App Service. A security breach occurs due to a vulnerability in the underlying operating system. According to the shared responsibility model, who is responsible for patching the OS vulnerability?

A) The customer is fully responsible
B) Microsoft is fully responsible
C) Responsibility is shared equally between customer and Microsoft
D) The customer must request Microsoft to patch, but Microsoft decides when

<details>
<summary>Answer</summary>

**Correct: B**

Azure App Service is PaaS. In PaaS, Microsoft is responsible for the OS, runtime, and patching. Customer only manages the application and data.

**Why the others are wrong:**
- Customer responsibility for OS only applies in IaaS (VMs), not PaaS services like App Service
- Responsibility is never shared equally - it's clearly divided by service layer. OS patching in PaaS is 100% Microsoft's responsibility
- Customer cannot request OS patches in PaaS - Microsoft handles all OS management automatically and transparently

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** A startup is launching a new mobile app and expects highly variable traffic - potentially zero users for days, then sudden spikes to thousands. They want to minimize costs during low-usage periods. Which pricing model provides the BEST cost optimization?

A) Consumption-based pricing (pay-as-you-go)
B) Reserved Instances with 3-year commitment
C) Hybrid Benefit licensing
D) Dedicated hardware with fixed monthly cost

<details>
<summary>Answer</summary>

**Correct: A**

Consumption-based pricing (OpEx model) charges only for resources actually used. With variable traffic including periods of zero usage, pay-as-you-go minimizes costs by scaling to zero during low usage. This is pure OpEx - no upfront cost.

**Why the others are wrong:**
- Reserved Instances require upfront commitment and payment regardless of usage - terrible for variable workloads with potential zero usage
- Hybrid Benefit is for existing license migration, not a pricing model for variable workloads, and still requires paying for compute instances
- Dedicated hardware has fixed costs regardless of usage - highest cost option for variable traffic patterns

</details>

---

**Q5.** Your company runs Azure Virtual Machines for production workloads. During a compliance audit, you discover data was exposed because network security groups (NSGs) were misconfigured. According to the shared responsibility model, who is responsible for this security breach?

A) Customer - they configured the NSG rules
B) Microsoft - they provide the NSG feature
C) Shared responsibility - both contributed to the breach
D) Third-party auditor - they should have caught it earlier

<details>
<summary>Answer</summary>

**Correct: A**

NSG configuration is customer responsibility in all service models. Microsoft provides the NSG tool, but customer configures the rules. Customer is always responsible for data, identity/access, and network controls they configure.

**Why the others are wrong:**
- Microsoft provides the NSG capability and ensures it functions correctly, but customer configures the actual rules - misconfiguration is customer responsibility
- This is not shared - network security configuration is explicitly customer responsibility. Microsoft's only responsibility is ensuring NSG feature works as designed
- Third-party auditor responsibility is irrelevant to the shared responsibility model between customer and cloud provider

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** A manufacturing company needs to replace aging servers. Option A: Purchase new servers for $500,000 upfront, $50,000 annual maintenance. Option B: Azure VMs with estimated $120,000 annual cost, no upfront payment. Over 3 years, ignoring time-value of money, which statement is TRUE?

A) Option B (Azure) is cheaper: $360,000 vs $650,000
B) Option A (on-premises) is cheaper: $650,000 vs $360,000
C) Both options cost exactly the same over 3 years
D) Cannot determine without knowing electricity costs

<details>
<summary>Answer</summary>

**Correct: A**

Option A (CapEx): $500k + ($50k × 3) = $650k. Option B (OpEx): $120k × 3 = $360k. This demonstrates CapEx (upfront capital + maintenance) vs OpEx (ongoing operational costs). Option B is $290k cheaper.

**Why the others are wrong:**
- This reverses the totals - simple math error. On-premises CapEx is higher in this scenario
- The costs are clearly different when calculated: $650k vs $360k
- While real TCO includes electricity, cooling, space, the question explicitly states 'ignoring time-value' and provides all numbers needed for comparison

</details>

---

**Q7.** A financial services company must keep certain data within their country's borders due to data sovereignty laws, but wants to use Azure services for other workloads. They also need the ability to fail over to a secondary region during disasters. Which combination BEST meets these requirements?

A) Public cloud only with geo-replication disabled
B) Private cloud only with no public cloud integration
C) Multi-cloud deployment with Azure and on-premises private cloud
D) Hybrid cloud with Azure Stack for on-premises and Azure regions for non-regulated workloads

<details>
<summary>Answer</summary>

**Correct: C**

Multi-cloud (on-premises private cloud + Azure public cloud) allows sovereign data to stay on-premises while other workloads use Azure. The on-premises component provides data sovereignty, Azure provides disaster recovery and additional services. This is technically a hybrid/multi-cloud architecture.

**Why the others are wrong:**
- Public cloud only cannot meet data sovereignty requirements - data must stay on-premises for regulated data
- Private cloud only doesn't provide Azure services or disaster recovery to Azure regions as requested
- While Azure Stack is a valid hybrid solution, 'multi-cloud with on-premises' is the BEST answer as it explicitly includes both on-premises sovereignty and Azure cloud services. Azure Stack wasn't mentioned in requirements.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** A company uses Azure SQL Database (PaaS). They ask who is responsible for ensuring the database is protected against distributed denial-of-service (DDoS) attacks at the network infrastructure level. What is the correct answer?

A) Customer must configure Azure DDoS Protection Standard
B) Responsibility is split: Microsoft provides hardware DDoS protection, customer must configure software rules
C) Customer must purchase third-party DDoS protection
D) Microsoft provides DDoS Protection Basic automatically at no additional cost

<details>
<summary>Answer</summary>

**Correct: D**

For PaaS services like Azure SQL Database, Microsoft is responsible for network infrastructure protection including DDoS Protection Basic, which is automatically enabled on all Azure services at no additional cost. This is physical and network layer protection.

**Why the others are wrong:**
- DDoS Protection Standard is optional enhanced protection - not required. Basic protection is automatic and free for all PaaS services
- DDoS protection at infrastructure level is entirely Microsoft's responsibility for PaaS - not split. Customer manages application-level security only
- Azure provides built-in DDoS Protection Basic - third-party solutions are unnecessary for infrastructure-level protection

</details>

---

