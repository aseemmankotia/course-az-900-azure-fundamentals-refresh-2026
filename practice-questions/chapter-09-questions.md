## Chapter 9: AZ-900 Exam Simulation and Test-Taking Strategy — Practice Questions

**Q1.** A company needs to deploy a web application that requires guaranteed uptime during planned Azure datacenter maintenance. The solution must minimize costs while ensuring the application remains available during single-datacenter failures. Which deployment approach BEST meets these requirements?

A) Deploy across multiple Azure Availability Zones within a single region
B) Deploy to a single Azure region using a single virtual machine with Premium SSD
C) Deploy across multiple Azure regions using Azure Traffic Manager
D) Deploy to a single availability set within one datacenter

<details>
<summary>Answer</summary>

**Correct: A**

Availability Zones provide 99.99% SLA and protect against datacenter failures within a region at lowest cost. They survive planned maintenance and single-datacenter outages.

**Why the others are wrong:**
- Single VM has no redundancy - maintenance or datacenter failure causes downtime, only 99.9% SLA
- Multi-region deployment is more expensive and complex than needed - overkill for datacenter-level protection
- Availability sets only protect against rack failures, not datacenter failures - still vulnerable during datacenter maintenance

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A development team needs to test application configurations without affecting production resources. They want to prevent accidental deletion of production resources while allowing full control over test resources. The solution must require LEAST administrative effort. Which combination of Azure features should they use?

A) Use Azure Policy to deny delete operations and organize resources using tags
B) Create separate subscriptions for production and test environments with resource locks on production
C) Apply ReadOnly locks to all production resources and use separate resource groups for test resources
D) Use Azure RBAC to assign developers Reader role on production and Contributor role on test resources

<details>
<summary>Answer</summary>

**Correct: D**

RBAC provides granular permission control with least effort - Reader role prevents modifications/deletions in production, Contributor allows full control in test. No lock management needed.

**Why the others are wrong:**
- Azure Policy creates compliance rules but is more complex than needed - tags don't prevent deletions, just organize resources
- Separate subscriptions work but require more administrative overhead - billing separation, multiple portals, subscription management
- ReadOnly locks prevent all modifications including legitimate updates - requires unlocking/relocking for every production change

</details>

---

**Q3.** A retail company experiences traffic spikes during holiday sales (10x normal load for 2 weeks yearly). Their application runs on virtual machines. Which Azure pricing model MOST cost-effectively handles this scenario?

A) Purchase 3-year Reserved VM Instances for peak capacity
B) Use Pay-As-You-Go pricing and manually scale VMs during holidays
C) Purchase 1-year Reserved Instances for baseline capacity and use Pay-As-You-Go for holiday spikes with autoscaling
D) Use Azure Spot VMs for all capacity with aggressive bidding

<details>
<summary>Answer</summary>

**Correct: C**

Hybrid approach: Reserved Instances (up to 72% savings) for predictable baseline load, Pay-As-You-Go with autoscaling for unpredictable 2-week spikes. Optimizes cost for both steady and burst workloads.

**Why the others are wrong:**
- Reserved Instances for peak capacity wastes money - paying for unused capacity 50 weeks/year at reserved rates
- Full Pay-As-You-Go works but misses 50-72% savings on baseline capacity that runs year-round
- Spot VMs can be evicted anytime - unacceptable for production retail during critical sales periods

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** A healthcare organization must ensure that patient data stored in Azure complies with data residency requirements, stays within Europe, and is protected from accidental administrator deletion. Which combination ensures compliance with LEAST complexity?

A) Deploy to any Azure region and use Azure Information Protection with encryption
B) Deploy to European Azure regions, apply resource locks, and enable Azure Policy for allowed locations
C) Use Azure Germany regions exclusively with Multi-Factor Authentication enabled
D) Deploy to European regions and configure Network Security Groups to block non-EU traffic

<details>
<summary>Answer</summary>

**Correct: B**

European regions ensure data residency, resource locks prevent deletion, Azure Policy enforces allowed locations - meets all requirements with standard features.

**Why the others are wrong:**
- Encryption protects data in transit/at rest but doesn't enforce geographic location - data could still be stored anywhere globally
- Azure Germany is being phased out and migrated to standard European regions - not recommended for new deployments
- NSGs control network traffic but don't enforce data storage location - data replication could still occur outside Europe

</details>

---

**Q5.** A company wants to migrate an on-premises SQL Server database to Azure. The database requires full control over the operating system for custom monitoring agents and has specialized performance tuning at OS level. Which Azure service BEST meets these requirements?

A) Azure SQL Database
B) Azure SQL Managed Instance
C) Azure Cosmos DB for PostgreSQL
D) SQL Server on Azure Virtual Machines

<details>
<summary>Answer</summary>

**Correct: D**

SQL Server on Azure VMs is IaaS - provides full OS access for custom agents and OS-level tuning. Complete control over SQL Server installation and configuration.

**Why the others are wrong:**
- Azure SQL Database is PaaS - no OS access, Microsoft manages underlying infrastructure completely
- Azure SQL Managed Instance is PaaS - no OS access, though provides more SQL Server features than SQL Database
- Cosmos DB uses different database engine (not SQL Server) - incompatible with SQL Server workloads

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** An organization needs to estimate the cost of migrating 50 on-premises servers to Azure, including cost comparison with current datacenter expenses over 5 years. Which Azure tool should they use?

A) Azure Pricing Calculator
B) Azure Cost Management and Billing
C) Azure Advisor cost recommendations
D) Total Cost of Ownership (TCO) Calculator

<details>
<summary>Answer</summary>

**Correct: D**

TCO Calculator specifically compares on-premises costs (hardware, power, cooling, admin labor) vs Azure costs over time. Designed for migration scenarios.

**Why the others are wrong:**
- Pricing Calculator estimates Azure costs only - doesn't compare with on-premises or calculate TCO
- Cost Management tracks actual spending after resources are deployed - not for pre-migration estimation
- Azure Advisor provides optimization recommendations for existing resources - not for pre-migration TCO analysis

</details>

---

**Q7.** A company has deployed resources across 5 Azure subscriptions. Management needs a single dashboard showing compliance status for all subscriptions against corporate security policies. Which Azure service provides this capability?

A) Azure Monitor with Log Analytics workspace
B) Azure Policy compliance dashboard
C) Microsoft Defender for Cloud
D) Azure Service Health

<details>
<summary>Answer</summary>

**Correct: C**

Microsoft Defender for Cloud provides unified security posture management across multiple subscriptions with compliance dashboard, secure score, and policy compliance tracking.

**Why the others are wrong:**
- Azure Monitor collects telemetry and logs but doesn't provide compliance assessment or security policy evaluation
- Azure Policy shows compliance per policy but doesn't aggregate cross-subscription security posture - no unified security dashboard
- Service Health shows Azure platform health and outages - not security compliance status

</details>

---

**Q8.** A startup needs to deploy a Node.js web application quickly without managing servers, operating systems, or runtime environments. The solution must automatically scale based on HTTP requests and minimize operational overhead. Which Azure compute option is MOST appropriate?

A) Azure Virtual Machines with custom scaling scripts
B) Azure App Service
C) Azure Container Instances
D) Azure Kubernetes Service (AKS)

<details>
<summary>Answer</summary>

**Correct: B**

Azure App Service is PaaS for web apps - no server/OS management, built-in autoscaling based on HTTP requests, supports Node.js natively. Lowest operational overhead for web apps.

**Why the others are wrong:**
- Virtual Machines require managing OS, patching, scaling configuration - high operational overhead, IaaS model
- Container Instances don't provide built-in HTTP autoscaling or load balancing - requires additional configuration
- AKS requires Kubernetes knowledge and cluster management - excessive complexity for simple web app deployment

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

