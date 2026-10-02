## Chapter 2: Cloud Benefits: Availability, Scalability, and Reliability — Practice Questions

**Q1.** A company requires their customer-facing web application to maintain 99.99% availability. The application currently runs on a single Azure Virtual Machine. Which solution BEST meets this requirement while minimizing costs?

A) Upgrade to a larger VM size with more vCPUs and memory
B) Enable Azure Backup on the existing VM with hourly backup frequency
C) Configure auto-shutdown during off-peak hours to reduce costs
D) Deploy the application across multiple VMs in an Availability Set with at least 2 fault domains

<details>
<summary>Answer</summary>

**Correct: D**

Availability Sets distribute VMs across multiple fault domains and update domains, providing 99.95% SLA (which meets the 99.99% when combined with load balancing). This is the most cost-effective solution that achieves high availability through redundancy.

**Why the others are wrong:**
- Scaling up (vertical scaling) increases capacity but doesn't improve availability - if the single VM fails, the application goes down regardless of VM size
- Backups help with disaster recovery but don't prevent downtime during VM failure - restore time violates the 99.99% availability requirement (52.56 minutes max downtime per year)
- Auto-shutdown actively reduces availability by intentionally taking the application offline - this contradicts the 99.99% requirement

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A retail application experiences predictable traffic spikes every day from 9 AM to 6 PM, requiring 10 VMs during peak hours but only 2 VMs during off-hours. Which Azure capability should be configured to handle this pattern?

A) Vertical scaling with scheduled VM resizing
B) High availability with availability zones
C) Disaster recovery with Azure Site Recovery
D) Elasticity with scheduled autoscaling rules

<details>
<summary>Answer</summary>

**Correct: D**

Elasticity is the automatic ability to scale resources based on demand. Scheduled autoscaling rules can automatically add VMs at 9 AM and remove them at 6 PM, matching the predictable pattern. This optimizes cost by only paying for resources when needed.

**Why the others are wrong:**
- Vertical scaling changes VM size (scale up/down) but doesn't address the need to add/remove instances - you'd still pay for idle capacity during off-hours
- Availability zones provide geographic redundancy for high availability but don't automatically adjust capacity based on demand - you'd run all VMs 24/7
- Azure Site Recovery is for disaster recovery and business continuity, not for handling routine daily traffic patterns

</details>

---

**Q3.** An organization needs to ensure their Azure SQL Database can automatically recover from datacenter failures without manual intervention. Which Azure feature provides this capability?

A) Vertical scaling to Premium tier
B) Point-in-time restore
C) Geo-replication with automatic failover groups
D) Read-scale replicas

<details>
<summary>Answer</summary>

**Correct: C**

Geo-replication with automatic failover groups creates readable secondary databases in different regions and automatically fails over when the primary region becomes unavailable. This provides automatic recovery without manual intervention, ensuring business continuity.

**Why the others are wrong:**
- Upgrading to Premium tier increases performance but doesn't provide automatic datacenter-level failover - the database would still be unavailable if the datacenter fails
- Point-in-time restore requires manual action to restore the database and involves downtime - it doesn't meet the 'automatic recovery without manual intervention' requirement
- Read-scale replicas improve read performance but don't provide automatic write failover - if the primary fails, you can't write to the read replicas

</details>

---

**Q4.** A company is comparing cloud costs between two scenarios: Scenario A with 99.9% SLA and Scenario B with 99.99% SLA. What is the maximum additional downtime per month that Scenario A allows compared to Scenario B?

A) Approximately 4.3 minutes
B) Approximately 86 minutes
C) Approximately 43 minutes
D) Approximately 8.6 minutes

<details>
<summary>Answer</summary>

**Correct: C**

99.9% SLA = 43.2 minutes downtime per month. 99.99% SLA = 4.32 minutes downtime per month. Difference = 43.2 - 4.32 = 38.88 minutes, approximately 43 minutes. This calculation is frequently tested to ensure understanding of SLA impact.

**Why the others are wrong:**
- 4.3 minutes is the total allowed downtime for 99.99% SLA, not the difference between the two scenarios
- 86 minutes would be double the 99.9% SLA allowance - incorrect calculation
- 8.6 minutes doesn't correspond to either SLA or the difference between them

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** A development team needs to increase the processing power of their application server from 4 vCPUs to 8 vCPUs to handle increased computational demands. Which scaling approach describes this change?

A) Horizontal scaling (scale out)
B) Elastic scaling
C) Vertical scaling (scale up)
D) Geographic scaling

<details>
<summary>Answer</summary>

**Correct: C**

Vertical scaling (scale up) means increasing the resources of a single instance - more CPU, RAM, or storage. Changing from 4 to 8 vCPUs on the same server is vertical scaling. Exam frequently tests the distinction between vertical (up/down) and horizontal (out/in).

**Why the others are wrong:**
- Horizontal scaling means adding more instances (servers), not increasing resources on existing instance - this would be going from 1 server to 2 servers
- Elastic scaling is a general term for automatic scaling but doesn't specifically describe the vertical nature of this change
- Geographic scaling refers to deploying across regions for global reach, not increasing instance resources

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q6.** A financial services company must ensure they can predict their monthly Azure costs within 5% variance and guarantee consistent application performance during business hours. Which cloud benefit category addresses both requirements?

A) Predictability
B) High availability
C) Scalability
D) Elasticity

<details>
<summary>Answer</summary>

**Correct: A**

Predictability encompasses both cost predictability (forecasting expenses accurately) and performance predictability (consistent resource availability and response times). Azure Cost Management enables cost forecasting, while reserved capacity and SLAs enable performance predictability.

**Why the others are wrong:**
- High availability focuses on uptime and minimizing outages, not on cost forecasting or performance consistency
- Scalability is the ability to handle increased load but doesn't specifically address cost or performance predictability
- Elasticity is automatic scaling based on demand - while it can help with performance, it can introduce cost variability rather than predictability

</details>

---

**Q7.** An application currently handles 1,000 requests per second using 5 virtual machines. Traffic suddenly increases to 5,000 requests per second. The application automatically provisions 20 additional VMs within 3 minutes and removes them when traffic normalizes. Which cloud characteristic is demonstrated?

A) Reliability through redundancy
B) Elasticity through automatic scaling
C) Vertical scaling through VM resizing
D) Disaster recovery through failover

<details>
<summary>Answer</summary>

**Correct: B**

Elasticity is the ability to automatically and rapidly scale resources both up and down based on demand. The automatic addition of VMs when load increases and removal when load decreases demonstrates elasticity. The key is 'automatic' and 'bidirectional' scaling.

**Why the others are wrong:**
- Reliability through redundancy maintains availability but doesn't describe the automatic scaling behavior based on demand changes
- Vertical scaling would be resizing existing VMs (e.g., 4 vCPU to 8 vCPU), not adding more VM instances - this scenario describes horizontal scaling
- Disaster recovery addresses recovery from failures, not routine demand-based scaling

</details>

---

**Q8.** A company wants to enforce that all Azure resources must have specific tags (CostCenter, Environment, Owner) and that Storage Accounts must use encryption at rest. Which Azure capability should they implement?

A) Azure Monitor for resource tracking
B) Azure Advisor for best practice recommendations
C) Role-Based Access Control (RBAC) for permissions
D) Azure Policy for governance and compliance

<details>
<summary>Answer</summary>

**Correct: D**

Azure Policy enforces organizational standards and assesses compliance at scale. It can require specific tags on resources and enforce security configurations like encryption. Policy is the governance tool for enforcing rules across Azure resources.

**Why the others are wrong:**
- Azure Monitor collects and analyzes telemetry data but doesn't enforce compliance rules or prevent non-compliant resource creation
- Azure Advisor provides recommendations for optimization but doesn't enforce requirements - it's advisory, not preventive
- RBAC controls who can perform actions but doesn't enforce resource configuration standards like required tags or encryption settings

</details>

---

