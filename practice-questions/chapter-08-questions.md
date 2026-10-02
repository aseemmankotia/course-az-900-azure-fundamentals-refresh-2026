## Chapter 8: Azure Governance, Monitoring, and Management Tools — Practice Questions

**Q1.** A company wants to ensure that all storage accounts in their Azure subscription must have encryption enabled and public access disabled. They need this enforced automatically on all new storage accounts. Which solution BEST meets these requirements?

A) Create an Azure Resource Lock on the subscription to prevent changes to storage account settings
B) Assign an Azure Policy with Deny effect that rejects storage accounts without encryption and public access disabled
C) Configure Azure RBAC to remove permissions for users to create storage accounts without encryption
D) Use Azure Advisor recommendations to identify non-compliant storage accounts and manually fix them

<details>
<summary>Answer</summary>

**Correct: B**

Azure Policy with Deny effect prevents creation of non-compliant resources automatically. It evaluates resource properties during creation and blocks deployments that don't meet the policy definition. This is the correct tool for enforcing organizational standards.

**Why the others are wrong:**
- Resource locks prevent deletion/modification of existing resources but don't enforce configuration standards or prevent creation of non-compliant resources
- RBAC controls who can perform actions (permissions) but doesn't enforce how resources are configured. Users with permission could still create non-compliant storage accounts
- Azure Advisor provides recommendations but doesn't enforce or prevent anything. It's reactive (identifies issues after creation) not proactive enforcement

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An administrator accidentally deleted a critical resource group containing production databases. The company wants to prevent this from happening again while still allowing authorized users to modify resources within the group. What should they implement?

A) Apply a ReadOnly lock on the resource group
B) Remove delete permissions using Azure RBAC
C) Apply a CanNotDelete lock on the resource group
D) Create an Azure Policy with Deny effect to prevent deletions

<details>
<summary>Answer</summary>

**Correct: C**

CanNotDelete lock prevents deletion of the resource and child resources while still allowing modifications (updates, configuration changes). This meets both requirements: prevent accidental deletion while allowing authorized changes.

**Why the others are wrong:**
- ReadOnly lock prevents both modifications AND deletions. Users couldn't update configurations, scale resources, or make any changes - too restrictive for the requirement
- RBAC changes affect who can delete, but authorized admins often need delete permission for other tasks. Doesn't prevent accidental deletion by authorized users
- Azure Policy Deny effect is for enforcing configuration standards, not preventing deletions. Policies evaluate resource properties during deployment, not deletion operations

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A financial services company needs to discover, classify, and protect sensitive data across Azure SQL Database, Azure Storage, and on-premises SQL servers from a single dashboard. They also need automated compliance reports. Which Azure service should they use?

A) Azure Policy to enforce data protection standards across all data sources
B) Microsoft Purview to create a unified data governance solution
C) Azure Monitor with Log Analytics to track data access patterns
D) Azure Security Center to scan and protect databases

<details>
<summary>Answer</summary>

**Correct: B**

Microsoft Purview is the unified data governance service that discovers, classifies, and manages data across multi-cloud and on-premises environments. It provides automated scanning, data cataloging, sensitivity labeling, and compliance reporting from a single interface.

**Why the others are wrong:**
- Azure Policy enforces standards but doesn't discover, classify, or catalog data. It can't scan data sources or generate data governance reports
- Azure Monitor collects metrics and logs but doesn't perform data discovery, classification, or governance. It's for operational monitoring, not data governance
- Azure Security Center (now Defender for Cloud) focuses on security posture and threat protection, not data governance, discovery, or compliance reporting across data estates

</details>

---

**Q4.** A startup with limited IT staff needs to deploy 50 identical virtual machines across three Azure regions. They want the deployment to be repeatable, version-controlled, and minimize manual configuration errors. What approach should they use?

A) Create an ARM template or Bicep file defining the VM configuration and deploy it to each region
B) Use Azure Portal to manually create each VM and document the steps
C) Use Azure CLI commands in a script to create each VM sequentially
D) Configure one VM manually, then use Azure Site Recovery to replicate it to other regions

<details>
<summary>Answer</summary>

**Correct: A**

ARM templates and Bicep are Infrastructure as Code (IaC) solutions that define resources declaratively. They're repeatable, version-controlled (stored in Git), and eliminate manual errors. Single template can deploy to multiple regions with parameters. This is the Azure-native IaC approach.

**Why the others are wrong:**
- Manual portal creation is error-prone, time-consuming for 50 VMs, not repeatable, and can't be version-controlled. Violates all IaC principles
- Azure CLI scripts work but are imperative (step-by-step) not declarative. Harder to maintain, less idempotent than ARM/Bicep. Not the BEST approach for repeatable infrastructure
- Azure Site Recovery is for disaster recovery and business continuity, not infrastructure deployment. It replicates VMs for failover scenarios, not for multi-region deployment patterns

</details>

---

**Q5.** A company manages Azure resources, AWS EC2 instances, and on-premises VMware servers. They want to apply Azure Policy to ALL these environments and manage everything from Azure Portal. Which service enables this?

A) Azure Monitor to collect metrics from all environments
B) Azure Lighthouse for cross-tenant management
C) Azure Arc to project non-Azure resources into Azure Resource Manager
D) Azure Site Recovery to replicate workloads to Azure

<details>
<summary>Answer</summary>

**Correct: C**

Azure Arc projects on-premises and multi-cloud resources into Azure Resource Manager (ARM). Once Arc-enabled, these resources appear in Azure Portal and can have Azure Policy, RBAC, tags, and other Azure management tools applied to them as if they were native Azure resources.

**Why the others are wrong:**
- Azure Monitor can collect metrics from multiple environments but doesn't enable Azure Policy enforcement on non-Azure resources. It's for observability, not governance projection
- Azure Lighthouse is for managing multiple Azure tenants (service provider scenarios), not for managing non-Azure infrastructure. It doesn't project AWS or on-premises resources
- Azure Site Recovery replicates and protects workloads but doesn't provide unified management or policy enforcement across hybrid/multi-cloud environments

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** Your application is experiencing performance degradation. You need to identify which component is slow: the web tier, database queries, or external API calls. You also want automatic detection of anomalies. Which Azure service provides this?

A) Azure Service Health to check for Azure platform issues
B) Azure Advisor to get performance recommendations
C) Azure Monitor Metrics to view resource CPU and memory usage
D) Application Insights to track application performance and dependencies

<details>
<summary>Answer</summary>

**Correct: D**

Application Insights provides application performance monitoring (APM) with distributed tracing across components. It tracks request rates, response times, dependency calls (databases, APIs), and uses AI to detect anomalies automatically. Shows exactly where slowdowns occur in the application stack.

**Why the others are wrong:**
- Azure Service Health reports Azure platform outages and maintenance, not application-level performance issues within your code or dependencies
- Azure Advisor provides recommendations after analysis but doesn't provide real-time performance monitoring, distributed tracing, or anomaly detection for running applications
- Azure Monitor Metrics shows infrastructure-level metrics (CPU, memory, disk) but doesn't trace application requests through components or analyze application-specific performance bottlenecks

</details>

---

**Q7.** You receive an email from Azure that several regions will have planned maintenance in 72 hours that may affect your VMs. You need to know if YOUR specific resources are impacted and what actions to take. Which service provides this personalized information?

A) Azure Monitor alerts configured on your VM metrics
B) Azure Advisor recommendations for affected resources
C) Azure Service Health with health alerts for your subscription
D) Azure Status page showing global Azure health

<details>
<summary>Answer</summary>

**Correct: C**

Azure Service Health provides personalized notifications about Azure service issues, planned maintenance, and health advisories that specifically affect YOUR resources. It shows which of your resources are impacted and recommended actions. Can configure alerts for proactive notification.

**Why the others are wrong:**
- Azure Monitor alerts trigger based on metric thresholds (CPU, memory) not Azure platform maintenance events. It monitors resource performance, not Azure service health
- Azure Advisor provides best practice recommendations for cost, security, reliability, and performance - not real-time service health notifications or planned maintenance alerts
- Azure Status page shows global Azure health for all regions/services but isn't personalized to your resources. You'd have to manually determine if your resources are affected

</details>

---

**Q8.** An IT manager wants to reduce Azure costs. They need actionable recommendations on underutilized VMs, unattached disks, and reserved instance opportunities based on their actual usage patterns. Which service provides this?

A) Azure Cost Management for viewing current spending and trends
B) Azure Advisor to get personalized cost optimization recommendations
C) Azure Monitor to identify resources with low CPU utilization
D) Azure Policy to enforce resource tagging for cost tracking

<details>
<summary>Answer</summary>

**Correct: B**

Azure Advisor analyzes resource configuration and usage telemetry to provide personalized recommendations across five categories: Cost, Security, Reliability, Operational Excellence, and Performance. Cost recommendations include right-sizing VMs, deleting unattached resources, and reserved instance opportunities based on actual usage.

**Why the others are wrong:**
- Azure Cost Management shows spending data and trends but doesn't analyze usage patterns to generate recommendations. It's for tracking and analyzing costs, not generating optimization suggestions
- Azure Monitor collects metrics like CPU utilization but doesn't provide cost-saving recommendations or identify unattached resources. It's for observability, not cost optimization guidance
- Azure Policy enforces standards and can require tags for cost tracking, but doesn't analyze usage or generate cost-saving recommendations. It's for governance, not cost optimization advice

</details>

---

