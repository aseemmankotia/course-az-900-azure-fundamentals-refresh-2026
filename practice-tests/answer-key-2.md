# Answer Key — Practice Test 2

**Q1. Correct: B**

In the shared responsibility model, Microsoft always handles physical infrastructure (datacenters, cooling, power, physical security), while customers retain control over their data, including encryption key management, data classification, and identity/access management. This allows the customer to prove Microsoft cannot access their data by using customer-managed keys (CMK) or bring-your-own-key (BYOK) solutions.

---

**Q2. Correct: B**

Hybrid approach optimizes cost by using reserved instances (1-year or 3-year commitments with up to 72% discount) for predictable baseline load, while leveraging consumption-based pricing's elasticity for unpredictable spikes. You only pay for peak capacity when actually needed (3-4 times/year), avoiding wasted reserved capacity costs for 99% of the year.

---

**Q3. Correct: A**

IaaS (Azure Virtual Machines) provides full control over the OS, registry, and installed software while Microsoft handles physical infrastructure (compute, storage, networking hardware). You can upload custom VHD images with Windows Server 2012, specific patches, and registry modifications. Customer manages OS, applications, and runtime; Microsoft manages virtualization layer and below.

---

**Q4. Correct: A**

High availability (99.99% SLA achieved through Azure Availability Zones and multi-region deployments) combined with geo-distribution (deploying across multiple Azure regions) directly addresses uptime requirements and regional failover. Azure Traffic Manager, Azure Front Door, or geo-replicated databases enable automatic failover within seconds with geo-redundant storage (GRS) or zone-redundant storage (ZRS) ensuring zero data loss through synchronous replication.

---

**Q5. Correct: C**

Public cloud with Azure's 60+ regions worldwide allows deploying resources in specific geographic regions (e.g., Germany West for German data, Japan East for Japanese data). Azure Policy can enforce that specific customer datasets never leave designated regions, ensuring data residency compliance. Azure Active Directory provides unified identity across all regions while data stays geo-locked. This is more cost-effective and manageable than 15 separate private clouds.

---

**Q6. Correct: C**

Azure Batch (IaaS) provides job scheduling, automatic VM provisioning/deprovisioning, and supports low-priority VMs (up to 80% discount vs regular VMs). Scales to 500 cores for 8 hours, then auto-scales to zero - you pay only for 8 hours of compute monthly. Provides full OS control for custom libraries and system dependencies (root access). Estimated cost: ~$240-600/month (8 hours @ low-priority) vs $12,000 always-on.

---

**Q7. Correct: D**

Azure SQL Database with customer-managed TDE keys in Azure Key Vault provides the required control over encryption keys, on-demand rotation capabilities, complete audit logging through Key Vault, while maintaining a PaaS model with minimal administrative overhead. This demonstrates the shared responsibility model where Microsoft manages the infrastructure and availability while the customer controls the encryption keys.

---

**Q8. Correct: B**

The consumption-based pricing model (pay-as-you-go) directly addresses their concern about upfront costs and variable traffic. They pay only for actual resource consumption during each hour, avoiding costs during low-usage periods (100 requests/hour) and automatically scaling costs with high-usage periods (50,000 requests/hour). This OpEx model eliminates large CapEx investments.

---

**Q9. Correct: D**

IaaS (Infrastructure as a Service) via Azure Virtual Machines provides complete control over the OS, ability to install custom kernel modules, specific hardware configurations, and full administrative access required for compliance auditing. This is the appropriate use case for IaaS when applications require OS-level control and cannot be refactored.

---

**Q10. Correct: B**

Hybrid cloud deployment combines their on-premises legacy systems with Azure public cloud services across multiple regions (US and EU). This model addresses data residency requirements by using Azure regions in appropriate geographies while maintaining connectivity to on-premises systems. Azure Arc and other tools enable unified management across hybrid environments.

---

**Q11. Correct: C**

High availability (using availability zones, load balancers, and rolling updates) eliminates the need for scheduled downtime during updates by keeping the application accessible. Reliability ensures automatic recovery from individual component failures without manual intervention. Together these address both zero-downtime updates and self-healing requirements.

---

**Q12. Correct: D**

In the shared responsibility model, Microsoft provides ISO 27001 certification (customer obtains/verifies documentation from Compliance Manager), but customers must configure Azure Activity Log retention periods and implement Azure Policy to enforce their governance requirements. Microsoft provides the governance tools; customers must configure and use them.

---

**Q13. Correct: C**

Azure sovereign regions (such as Azure Government, Azure China, Azure Germany) are physically and logically isolated instances of Azure designed to meet specific compliance, sovereignty, and regulatory requirements. They operate independently from the public Azure cloud and ensure data residency within specific national boundaries.

---

**Q14. Correct: C**

Azure Kubernetes Service (AKS) is a managed Kubernetes orchestration service that provides automatic scaling, load balancing, self-healing, rolling updates, and built-in monitoring. AKS manages the Kubernetes control plane while you focus on your containers, meeting all requirements including the specific request for Kubernetes.

---

**Q15. Correct: A**

Azure ExpressRoute provides private, dedicated connectivity between on-premises infrastructure and Azure through a connectivity provider. It does not traverse the public internet, offers predictable performance, supports up to 100 Gbps bandwidth, and provides lower latencies than typical internet connections - perfect for financial services requirements.

---

**Q16. Correct: B**

Azure Blob Storage Archive tier is specifically designed for rarely accessed data with the lowest storage cost (approximately $0.00099 per GB/month as of 2026). It can tolerate retrieval times of several hours (rehydration process), making it perfect for compliance archives accessed once yearly. The 180-day minimum storage duration is acceptable for 10-year retention.

---

**Q17. Correct: B**

Single Sign-On (SSO) allows users to sign in once with corporate credentials and access multiple applications without re-authentication. Multi-Factor Authentication (MFA) provides the additional verification requirement (authentication app) when signing in, especially from unknown devices. This combination directly addresses both stated requirements.

---

**Q18. Correct: C**

Azure AI Vision includes Content Safety API (part of Azure AI services) which provides pre-built content moderation capabilities for images without requiring custom model training. Microsoft's Responsible AI Standard encompasses transparency, accountability, and other principles (fairness, reliability, privacy, inclusiveness, security) that guide the ethical use of AI services - specifically applicable to Azure AI services as of the January 2026 exam update.

---

**Q19. Correct: A**

Azure AI Language (part of Azure AI services) provides pre-built NLP capabilities including sentiment analysis, key phrase extraction, and entity recognition specifically designed for text analytics scenarios. It supports data residency requirements through regional deployment and integrates natively with other Azure services. This is the purpose-built service for extracting insights from text documents without requiring custom model development.

---

**Q20. Correct: D**

Azure Container Apps (built on Container Instances) provides serverless container hosting with automatic HTTP-based scaling that can scale to zero instances when idle. It scales rapidly (within seconds) based on HTTP traffic and uses consumption-based pricing where you only pay during request processing. This eliminates costs during idle periods while handling unpredictable spikes efficiently—perfect for stateless containerized applications with variable traffic.

---

**Q21. Correct: D**

Geo-zone-redundant storage (GZRS) provides synchronous replication across three availability zones in the primary region (protecting against zone failures) AND asynchronous replication to a paired secondary region (protecting against region failures). The synchronous ZRS component in the primary region ensures minimal data loss (RPO near zero) for zone failures, while the geo-replication provides region-level protection. This is the only option that addresses both availability zone AND region failures with the required RPO.

---

**Q22. Correct: A**

Azure Bastion provides secure RDP/SSH connectivity to VMs through the Azure portal over TLS without requiring public IP addresses on the VMs. When combined with Microsoft Defender for Cloud's just-in-time (JIT) VM access, it enforces time-limited access requests with approval workflows and maintains detailed audit logs. This eliminates public exposure of management ports while providing the requested access control and auditing capabilities.

---

**Q23. Correct: B**

Management groups provide hierarchical organization of subscriptions with policy inheritance. The parent company can create a management group structure (e.g., root > regions > subsidiaries) and apply Azure Policies at the regional management group level that restrict allowed locations. Each subsidiary gets its own subscription under the appropriate regional management group, inheriting region restrictions automatically while maintaining billing separation. This provides centralized governance with delegated administration and consolidated cost visibility across all subscriptions.

---

**Q24. Correct: B**

Azure Container Instances (ACI) provides per-second billing for containerized workloads with no infrastructure management. For a 2-3 hour job running once weekly, ACI charges only for actual compute time used (approximately 2.5 hours/week). The container can be started on-demand through automation (Azure Logic Apps, Functions, or Automation accounts), processes the blob storage data, and terminates when complete. This eliminates costs during the remaining 165+ hours of the week, making it the most cost-effective option for infrequent batch workloads.

---

**Q25. Correct: D**

Azure region pairs provide automatic geo-replication for supported services within the same geography (Europe), maintain data residency requirements, and offer built-in disaster recovery with minimal administrative overhead. Azure AI services leverage region pairing for business continuity, ensuring that if North Europe fails, services can failover to the paired West Europe region while keeping data within European boundaries.

---

**Q26. Correct: B**

AKS with Horizontal Pod Autoscaler (HPA) and cluster autoscaler provides the optimal solution for containerized workloads with variable demand. HPA automatically scales pod replicas based on CPU/memory metrics to maintain performance during spikes, while cluster autoscaler adjusts the underlying node count to minimize costs during low-traffic periods. This combination handles both rapid scaling for sub-second response times and cost optimization for the dramatic traffic variations described.

---

**Q27. Correct: A**

Azure Data Box Heavy is specifically designed for bulk data migrations of 500 TB to 1 PB. With 500 TB to transfer over a 1 Gbps connection (limited to 200 Mbps during business hours), a network transfer would take approximately 40-50 days of continuous transfer time - far exceeding the 2-week requirement. Data Box Heavy allows copying data locally at disk speeds (no network impact), then ships the device to Microsoft for direct upload to Azure storage, completing within the 2-week timeframe.

---

**Q28. Correct: C**

Microsoft Entra External ID (formerly Azure AD B2B) enables secure collaboration with external partners without creating permanent credentials in your directory. Combined with Conditional Access policies, you can enforce Zero Trust principles by requiring device compliance checks and location-based restrictions on EVERY sign-in attempt. This implements the core Zero Trust tenet of 'never trust, always verify' by validating identity, device state, and location continuously rather than relying on network perimeter security.

---

**Q29. Correct: C**

Azure AI Content Safety is Microsoft's dedicated service for implementing responsible AI safeguards in generative AI applications. It provides pre-built capabilities to detect and filter harmful content categories, identify PII in inputs/outputs, apply custom blocklists (such as preventing medical diagnoses), and maintain detailed content filtering logs for compliance auditing. When integrated with Azure OpenAI Service, it enforces responsible AI principles at the model interaction layer, specifically addressing the requirements stated in the scenario.

---

**Q30. Correct: C**

A CanNotDelete lock allows users to read and modify resources but prevents deletion of the resource group and resources within it. This meets both requirements: prevents accidental deletion while allowing configuration updates.

---

**Q31. Correct: B**

Azure CLI is available in Cloud Shell and can deploy Bicep templates (Infrastructure as Code). Bicep provides a declarative syntax that can be version-controlled, reused, and is the modern recommended approach for Azure IaC over ARM JSON templates.

---

**Q32. Correct: A**

The TCO Calculator is specifically designed to compare on-premises infrastructure costs (including datacenter expenses, utilities, staff, hardware lifecycle) against Azure cloud costs over a multi-year period, typically 1-5 years.

---

**Q33. Correct: C**

Tags are metadata key-value pairs that can be applied to resources regardless of resource group. Microsoft Cost Management can filter and group costs by tags, making this the ideal solution for cross-resource-group cost tracking by department without reorganizing resources.

---

**Q34. Correct: B**

Azure Service Health provides personalized alerts and guidance for Azure service issues, planned maintenance, and health advisories. It shows current incidents, root cause analysis (RCA) when available, and allows subscriptions to specific service health events affecting your resources.

---

**Q35. Correct: A**

Azure Arc extends Azure management capabilities (including Azure Policy, Azure Monitor, RBAC) to resources outside Azure, including on-premises servers, other cloud providers' VMs (AWS, Google Cloud), and Kubernetes clusters, providing a unified control plane.

---

**Q36. Correct: D**

Tags are metadata key-value pairs that can be applied to existing resources without disruption. Microsoft Cost Management natively supports cost analysis by tags, allowing the finance team to filter, group, and allocate costs by department tag. This requires no resource moves, no additional services, and can be implemented immediately on existing deployments.

---

**Q37. Correct: D**

The TCO Calculator is specifically designed to compare on-premises costs versus Azure costs over time (typically 3-5 years). It includes on-premises factors like hardware depreciation, power, cooling, datacenter space, IT labor, and software licensing, then compares against Azure service costs to show potential savings. This is the exact scenario the TCO Calculator addresses.

---

**Q38. Correct: A**

A CanNotDelete lock prevents deletion of the resource but still allows modifications (updates). This exact lock type meets both requirements: administrators can add subnets, change configurations, or update settings, but no one can delete the Virtual Network until the lock is removed. CanNotDelete locks work regardless of RBAC permissions—even subscription owners cannot delete a locked resource.

---

**Q39. Correct: A**

Azure Policy with the 'Deny' effect prevents resource creation or modification that doesn't comply with defined rules. This policy can evaluate storage account settings during creation and block (deny) the operation if encryption is disabled or if Cool/Archive tiers are configured. This provides proactive, automated enforcement that works before non-compliant resources are deployed, regardless of user permissions.

---

**Q40. Correct: D**

ARM templates and Bicep are Infrastructure as Code (IaC) declarative languages that define the desired state of infrastructure. They can be version-controlled (Git), reused across regions, and provide idempotent deployments. Bicep (or ARM JSON) is the Azure-native IaC solution that meets all requirements: declarative, automatable, version-controllable, and reusable. This aligns with modern IaC best practices.

---

**Q41. Correct: D**

Azure Arc extends Azure Resource Manager (ARM) to manage non-Azure resources including AWS instances, on-premises VMware VMs, and servers in other clouds. Once Arc-enabled, these resources appear in Azure and can be governed with Azure Policy, monitored with Azure Monitor, and secured with Azure Security Center/Defender. Arc is specifically designed for projecting Azure management and governance to hybrid and multi-cloud environments.

---

**Q42. Correct: C**

Tags can be applied to existing resources without modification or redeployment. Microsoft Cost Management natively supports cost analysis filtering and grouping by tags, making this the fastest and most efficient solution. Tags are specifically designed for cross-cutting organizational metadata like department and environment that don't align with subscription boundaries.

---

**Q43. Correct: A**

Resource locks (CanNotDelete or ReadOnly) apply to all users regardless of their RBAC role assignments, including Owners and subscription administrators. A CanNotDelete lock prevents deletion and modification of the resource. The lock must be removed before deletion can proceed. Locks are specifically designed to prevent accidental deletion even by highly privileged users.

---

**Q44. Correct: D**

Bicep is Azure's native domain-specific language for declarative infrastructure as code. It compiles to ARM templates and is natively supported by Azure Resource Manager without additional tool installation. Bicep provides human-readable syntax (more readable than JSON), supports what-if operations to preview changes, and integrates with Azure CLI/PowerShell which are pre-installed on Microsoft-hosted Azure DevOps agents. As of 2026, Bicep is Microsoft's recommended IaC approach for Azure.

---

