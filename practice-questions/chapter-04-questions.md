## Chapter 4: Azure Regions, Availability Zones, and Resource Organization — Practice Questions

**Q1.** A company requires that all customer data remains within European borders due to GDPR compliance. The company also needs automatic failover to a secondary location within Europe if the primary region fails. Which Azure feature BEST addresses both requirements?

A) Deploy resources across multiple availability zones in West Europe region
B) Deploy resources in West Europe region with automatic replication to the paired North Europe region
C) Deploy resources in multiple sovereign regions within Europe
D) Deploy resources using Azure Arc to manage on-premises European datacenters

<details>
<summary>Answer</summary>

**Correct: B**

Region pairs provide automatic geographic replication for disaster recovery while maintaining data residency within the same geography (Europe). West Europe is paired with North Europe, both within European boundaries, meeting GDPR requirements and providing cross-region disaster recovery.

**Why the others are wrong:**
- Availability zones provide high availability within a single region but do not provide cross-region disaster recovery if the entire region fails
- Sovereign regions (Azure Government, Azure China) are for specific governmental/regulatory requirements and are not within standard European geography
- Azure Arc extends Azure management to on-premises and multi-cloud but doesn't provide Azure's native region pair disaster recovery capabilities

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** An application requires 99.99% SLA and must survive datacenter-level failures within a region. The company wants to minimize cross-region data transfer costs. Which deployment strategy should be used?

A) Deploy across region pairs with active-active configuration
B) Deploy to multiple resource groups in the same region
C) Deploy using management groups with geo-redundant backup
D) Deploy resources across three availability zones within a single region

<details>
<summary>Answer</summary>

**Correct: D**

Availability zones are physically separate datacenters within the same region, providing 99.99% SLA while keeping all traffic within the region (no cross-region data transfer costs). Three zones provide redundancy against datacenter failure without geographic distribution costs.

**Why the others are wrong:**
- Region pairs require cross-region data transfer which increases costs; active-active across regions is more expensive than needed for this requirement
- Resource groups are logical containers and provide no availability or redundancy benefits
- Management groups organize subscriptions for governance but provide no infrastructure redundancy or SLA improvements

</details>

---

**Q3.** A development team accidentally deletes a resource group containing production virtual machines. What happens to the resources?

A) All resources in the resource group are permanently deleted
B) Resources are moved to a default resource group and remain running
C) Resources are retained for 30 days in a soft-deleted state
D) Only the resource group metadata is deleted; resources remain accessible

<details>
<summary>Answer</summary>

**Correct: A**

Resource groups have a lifecycle dependency with their resources. When a resource group is deleted, ALL resources contained within it are permanently deleted. This is a critical exam concept about resource group properties.

**Why the others are wrong:**
- Azure does not automatically move resources to another resource group; they are deleted with the parent group
- Soft delete exists for specific resources like Key Vault and Storage blobs, but is not a general resource group feature
- Resource group deletion cascades to all contained resources; the resources do not remain accessible independently

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** A company has 15 Azure subscriptions across development, testing, and production environments. They need to apply a policy that prevents the creation of resources in the Brazil South region across all subscriptions. What is the MOST efficient approach?

A) Apply the Azure Policy to each of the 15 subscriptions individually
B) Create a single resource group and apply the policy to that resource group
C) Create a management group, move all 15 subscriptions into it, and apply the policy at the management group level
D) Use Azure Advisor to recommend region restrictions for each subscription

<details>
<summary>Answer</summary>

**Correct: C**

Management groups allow policy inheritance across multiple subscriptions. Applying the policy once at the management group level automatically enforces it on all 15 child subscriptions, reducing administrative overhead and ensuring consistent governance.

**Why the others are wrong:**
- Applying policy to each subscription works but requires 15 separate configurations and increases management complexity
- Resource groups exist within subscriptions and cannot span multiple subscriptions; a policy at this level wouldn't affect the required scope
- Azure Advisor provides recommendations but does not enforce policies or prevent resource creation

</details>

---

**Q5.** A financial services company requires complete data isolation from public Azure due to regulatory requirements. Which Azure option should they use?

A) Azure Government sovereign cloud
B) Azure private regions with VPN connectivity
C) Availability zones with network security groups
D) Azure dedicated hosts in a standard region

<details>
<summary>Answer</summary>

**Correct: A**

Azure Government is a sovereign cloud with physical and logical network isolation from public Azure, designed for US government agencies and regulated industries requiring strict compliance and data sovereignty.

**Why the others are wrong:**
- Azure does not offer 'private regions' as a service; regions are either public or sovereign (Government, China)
- Availability zones and NSGs provide infrastructure redundancy and network security but not sovereign cloud isolation
- Dedicated hosts provide physical server isolation but still operate within public Azure and don't meet sovereign cloud requirements

</details>

---

**Q6.** An organization wants to assign different IT teams permission to manage resources, with the network team controlling all virtual networks and the compute team managing all VMs. Resources are currently deployed across 8 resource groups in one subscription. What is the BEST way to implement this access control?

A) Assign RBAC roles at the subscription level and use resource tags to differentiate permissions
B) Create separate subscriptions for network and compute resources, assign RBAC at subscription level
C) Assign RBAC roles at individual resource level for each VNET and VM
D) Reorganize resources so all VNets are in one resource group and all VMs in another, then assign RBAC at resource group level

<details>
<summary>Answer</summary>

**Correct: D**

Resource groups are a natural RBAC scope boundary. Organizing resources by team responsibility and assigning roles at the resource group level provides clear, manageable permissions. This aligns with the exam concept that resource groups serve as both a lifecycle container and an RBAC boundary.

**Why the others are wrong:**
- Tags do not affect RBAC permissions; they're metadata for organization and billing but don't control access
- Creating separate subscriptions works but is excessive overhead for this scenario; subscriptions are better for billing and major organizational boundaries
- Managing RBAC on hundreds of individual resources is administrative overhead and error-prone compared to resource group-level permissions

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** A resource group contains 10 virtual machines in West US region. Can this resource group also contain a storage account deployed to East US region?

A) No, all resources in a resource group must be in the same region as the resource group
B) Yes, but only if the regions are in the same geography (North America)
C) Yes, resource groups can contain resources from multiple regions
D) No, storage accounts must always be in the same region as compute resources they serve

<details>
<summary>Answer</summary>

**Correct: C**

Resource groups are logical containers and can contain resources from any region. The resource group location only determines where the resource group metadata is stored, not where resources must be deployed. This is a commonly tested concept.

**Why the others are wrong:**
- Resource group location is independent of resource locations; this is metadata location only
- Resources in a resource group can be in any region globally, not restricted to geography
- Storage accounts and compute resources can be in different regions; proximity affects latency but is not a deployment restriction

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** Which statement correctly describes the relationship between management groups and subscriptions?

A) Each subscription can belong to multiple management groups for flexible organization
B) Subscriptions automatically inherit all resource groups from their parent management group
C) Management groups provide billing consolidation across multiple subscriptions
D) Management groups can contain other management groups, creating a hierarchy up to 6 levels deep (excluding root)

<details>
<summary>Answer</summary>

**Correct: D**

Management groups support nesting up to 6 levels deep (excluding the root management group), creating a tree structure of up to 7 levels total including root. This hierarchy allows for granular policy and access control inheritance.

**Why the others are wrong:**
- Each subscription belongs to exactly ONE management group at a time; multiple membership would create conflicting policy inheritance
- Resource groups exist within subscriptions and are not inherited from management groups; management groups organize subscriptions, not resource groups
- Management groups provide governance (policies, RBAC) not billing consolidation; subscriptions remain the billing boundary

</details>

---

