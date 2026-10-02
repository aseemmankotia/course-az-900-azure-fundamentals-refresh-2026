## Chapter 7: Azure Cost Management and Pricing — Practice Questions

**Q1.** A company is migrating a web application from on-premises to Azure. The application consists of 10 VMs that run 24/7, 5 TB of file storage, and a SQL database. Management wants to estimate the total cost savings over 5 years. Which tool should they use?

A) Azure Total Cost of Ownership (TCO) Calculator to compare on-premises vs Azure costs
B) Azure Pricing Calculator to estimate monthly costs and multiply by 60 months
C) Microsoft Cost Management + Billing to analyze current spending patterns
D) Azure Advisor to get cost optimization recommendations

<details>
<summary>Answer</summary>

**Correct: A**

TCO Calculator is specifically designed to compare on-premises infrastructure costs (hardware, datacenter, power, cooling, IT labor) against Azure costs over a multi-year period. It factors in both direct and indirect costs of running infrastructure on-premises.

**Why the others are wrong:**
- Pricing Calculator estimates costs for NEW Azure workloads only — it doesn't include on-premises comparison or factor in datacenter exit costs, which are critical for migration ROI
- Cost Management + Billing tracks actual spending on existing Azure resources — it can't estimate or compare costs before migration
- Azure Advisor provides optimization recommendations for existing Azure resources — it can't compare on-premises vs cloud or estimate pre-migration costs

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A development team needs to estimate the monthly cost of deploying a new application to Azure. The application will use 3 B2s VMs in West US, 500 GB of Blob Storage in the Hot tier, and Azure SQL Database (General Purpose, 8 vCores). Which tool provides this estimate?

A) Azure Pricing Calculator
B) Azure Total Cost of Ownership (TCO) Calculator
C) Microsoft Cost Management + Billing
D) Azure Advisor Cost Recommendations

<details>
<summary>Answer</summary>

**Correct: A**

Azure Pricing Calculator is designed to estimate costs for new Azure workloads. You select specific services, configurations, and regions to get a monthly or annual cost estimate before deploying resources.

**Why the others are wrong:**
- TCO Calculator compares on-premises vs Azure total ownership costs — it's for migration decisions, not new workload estimates
- Cost Management + Billing analyzes actual spending on deployed resources — it can't estimate costs for resources that don't exist yet
- Azure Advisor provides optimization recommendations for existing resources — it doesn't estimate costs for new deployments

</details>

---

**Q3.** A company has Azure VMs spread across multiple departments. Finance wants to track how much each department spends on Azure resources for chargeback purposes. What is the MOST effective approach?

A) Create separate Azure subscriptions for each department
B) Apply tags to resources with department names and use Cost Management to filter by tag
C) Use Azure Policy to enforce resource naming conventions with department prefixes
D) Generate monthly Cost Management reports and manually sort resources by name

<details>
<summary>Answer</summary>

**Correct: B**

Tags are the recommended method for cost allocation. Cost Management can filter and group costs by tag values, providing automatic department-level cost breakdowns without manual effort or subscription sprawl.

**Why the others are wrong:**
- Separate subscriptions per department works but is administratively complex, limits resource sharing, and is overkill when tags solve the problem more elegantly
- Naming conventions help organization but Cost Management can't automatically group costs by resource name — you'd still need manual sorting
- Manual sorting is error-prone, time-consuming, and doesn't scale — tags with Cost Management automation is the correct pattern

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** A company runs batch processing jobs on Azure VMs that can tolerate interruptions and don't need to run continuously. The jobs typically run for 2-4 hours per day. Which pricing model provides the LOWEST cost?

A) Azure Spot VMs with eviction policies configured
B) Pay-as-you-go VMs that are started and stopped as needed
C) 1-year Reserved VM Instances
D) 3-year Reserved VM Instances with upfront payment

<details>
<summary>Answer</summary>

**Correct: A**

Spot VMs offer up to 90% discount compared to pay-as-you-go for workloads that can handle interruptions. Since the batch jobs tolerate interruptions and run only a few hours daily, Spot VMs are ideal and provide the deepest discount.

**Why the others are wrong:**
- Pay-as-you-go with start/stop saves costs vs 24/7 running but still costs more than Spot VMs — no discount on the hourly rate
- 1-year reservations provide ~40% savings but require commitment and only make sense for consistent 24/7 usage — not intermittent batch jobs
- 3-year reservations provide ~60% savings but require 3-year commitment — completely wrong for intermittent workloads and still costs more than Spot

</details>

---

**Q5.** A retail company runs VMs 24/7 for their e-commerce platform. Usage is consistent throughout the year. They want to reduce costs without changing architecture. Which approach provides the BEST long-term savings?

A) Configure auto-shutdown schedules to stop VMs during low-traffic hours
B) Migrate to Azure Spot VMs to get maximum discount
C) Purchase 3-year Reserved VM Instances for the production VMs
D) Use Azure Hybrid Benefit to apply existing Windows Server licenses

<details>
<summary>Answer</summary>

**Correct: C**

For consistent 24/7 workloads, 3-year Reserved Instances provide up to 72% savings compared to pay-as-you-go. The scenario states usage is consistent year-round, making reservations ideal.

**Why the others are wrong:**
- Auto-shutdown works for dev/test but would cause downtime for a 24/7 e-commerce platform — unacceptable for production
- Spot VMs can be evicted with 30-second notice — completely inappropriate for a production e-commerce platform that needs guaranteed availability
- Azure Hybrid Benefit reduces costs (up to 40%) but provides less savings than 3-year reservations (up to 72%) — reservations are the best option here

</details>

---

**Q6.** A company deployed 50 Standard D4s v5 VMs in East US region. They notice costs are higher than expected. Azure Advisor recommends downsizing 30 of these VMs to Standard D2s v5 because CPU utilization averages only 15%. What cost optimization strategy is this?

A) Right-sizing resources based on actual utilization
B) Using Reserved Instances for predictable workloads
C) Applying tags for cost allocation tracking
D) Configuring auto-scaling to match demand

<details>
<summary>Answer</summary>

**Correct: A**

Right-sizing means matching VM size to actual resource utilization. D4s v5 (4 vCPUs) costs more than D2s v5 (2 vCPUs). With 15% CPU usage, the VMs are oversized — downsizing saves money without impacting performance.

**Why the others are wrong:**
- Reserved Instances reduce hourly rate but don't address the core problem — VMs are oversized for the workload. You'd still be paying for capacity you don't use.
- Tags help track costs but don't reduce costs — they're for allocation and reporting, not optimization
- Auto-scaling adjusts VM count based on load, not VM size — the problem here is each VM is too large, not that there are too many VMs

</details>

---

**Q7.** A company has resources in West US region and wants to deploy identical resources in North Europe for disaster recovery. They notice the Azure Pricing Calculator shows different monthly costs for the same VM SKUs in both regions. What is the PRIMARY reason for this difference?

A) Network egress charges differ between regions based on distance
B) North Europe region has higher datacenter operational costs reflected in regional pricing
C) Reserved Instance discounts vary by region availability
D) Compute resources in Europe require VAT which increases the price

<details>
<summary>Answer</summary>

**Correct: B**

Azure pricing varies by region based on datacenter costs, local market conditions, and infrastructure expenses. Some regions (especially newer or geographically constrained ones) have higher base prices for the same resources. This is a heavily tested exam concept.

**Why the others are wrong:**
- Network egress charges exist but are separate line items — they don't affect the base VM hourly rate shown in Pricing Calculator
- Reserved Instance discounts are percentage-based and apply to regional pricing — they don't cause the base price difference between regions
- VAT is added at checkout for EU customers but isn't included in Pricing Calculator estimates — the calculator shows pre-tax pricing

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** A finance team wants to prevent Azure spending from exceeding $10,000 per month. They need to be notified when spending reaches 80% and 100% of this limit. Which Azure feature should they configure?

A) Azure Policy to deny resource creation when cost threshold is reached
B) Azure Advisor cost recommendations with custom threshold settings
C) Azure Service Health alerts for billing notifications
D) Azure Cost Management budgets with alert rules at 80% and 100%

<details>
<summary>Answer</summary>

**Correct: D**

Cost Management budgets allow you to set spending limits and configure alerts at percentage thresholds (e.g., 80%, 100%, 120%). Alerts are sent via email or action groups when thresholds are reached. This is the correct tool for proactive cost monitoring.

**Why the others are wrong:**
- Azure Policy enforces compliance rules but can't monitor or alert on spending — it doesn't have cost awareness or budget thresholds
- Azure Advisor provides cost optimization recommendations but doesn't support custom spending limits or proactive budget alerts
- Service Health alerts notify about Azure platform issues and outages — not related to cost monitoring or budget tracking

</details>

---

