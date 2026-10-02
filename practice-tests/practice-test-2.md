# Practice Test 2: AZ-900 Azure Fundamentals 2026: Complete Exam Preparation

- **Questions:** 44
- **Time limit:** 90 minutes
- **Passing score:** 70%%

> Answers are in `answer-key-2.md`. Track results in `score-tracker.md`.

---

**Q1.** A healthcare company is migrating its patient record system to Azure. The company must ensure that they maintain full control over encryption key management and can prove to auditors that Microsoft cannot access patient data. Under the shared responsibility model, which statement is correct?

A) The customer is responsible for physical security of the datacenter and Microsoft is responsible for data encryption
B) The customer is responsible for managing their own encryption keys and data classification, while Microsoft is responsible for physical infrastructure security
C) Microsoft is responsible for both physical security and all data encryption, while the customer only manages user access
D) The customer must provide their own physical servers in Azure datacenters to maintain full control over patient data

---

**Q2.** A startup with unpredictable traffic patterns is choosing between a consumption-based pricing model and a reserved capacity model for their Azure App Service. Their traffic can range from 100 users during off-hours to 50,000 users during flash sales (occurring 3-4 times per year). Which pricing approach BEST optimizes cost?

A) Purchase 3-year reserved capacity for peak load (50,000 users) to get maximum discount
B) Purchase reserved capacity for baseline load (100 users) and use consumption-based scaling for peak traffic spikes
C) Use consumption-based pricing (pay-per-execution) with automatic scaling for the entire workload
D) Use consumption-based pricing during off-hours and switch to reserved capacity before scheduled flash sales

---

**Q3.** An enterprise runs a legacy application that requires specific Windows Server 2012 patches and custom registry modifications. They want to migrate to Azure but must maintain these exact configurations for compliance reasons. After migration, they need Microsoft to handle physical hardware maintenance but want to retain full OS-level control. Which cloud service model meets these requirements?

A) IaaS - use Azure Virtual Machines with custom OS image
B) SaaS - use Azure Virtual Desktop with custom image deployment
C) PaaS - use Azure App Service with custom container deployment
D) Hybrid cloud - keep legacy system on-premises and use Azure for new workloads only

---

**Q4.** A financial trading platform requires 99.99% availability SLA and must process transactions within 50ms latency. During a regional Azure outage, the system must automatically failover to another region within 30 seconds with zero data loss. Which combination of cloud benefits directly addresses these requirements?

A) High availability and geo-distribution - multi-region deployment with automatic failover and data replication
B) Elasticity and agility - scale resources dynamically and deploy updates quickly
C) Reliability and predictability - consistent performance with cost forecasting
D) Security and governance - compliance controls with policy enforcement

---

**Q5.** A global manufacturing company operates factories in 15 countries with strict data residency laws requiring customer data to remain within national borders. They want to use a unified identity system and centralized management while ensuring data sovereignty. Which cloud deployment model satisfies these requirements?

A) Public cloud using Azure Government regions with dedicated instances per country
B) Private cloud with separate on-premises datacenters in each of the 15 countries
C) Public cloud using multiple Azure regions with Azure Policy enforcing geo-fencing per customer dataset
D) Hybrid cloud combining on-premises systems for data storage with Azure for compute and identity management

---

**Q6.** A university research department has a data processing job that runs once per month, consumes 500 compute cores for exactly 8 hours, then requires zero resources for the remaining 29-30 days. The job uses custom Python libraries and requires root access to install system dependencies. Total monthly compute cost with always-on dedicated VMs is $12,000. Which approach reduces cost while meeting technical requirements?

A) PaaS using Azure Functions Premium with pre-warmed instances to avoid cold starts
B) IaaS using Azure Virtual Machines with automatic shutdown/startup schedules and deallocate when stopped
C) IaaS using Azure Batch with low-priority VMs that auto-scale to zero after job completion
D) SaaS using Azure Databricks serverless compute pools with auto-termination after job completion

---

**Q7.** A financial services company is migrating its customer database to Azure. The company's compliance team requires full control over database encryption keys, the ability to rotate keys on-demand, and complete audit logs of all key access. The database must remain accessible 24/7 with minimal administrative overhead. Which solution BEST meets these requirements?

A) Use Azure SQL Database with Transparent Data Encryption (TDE) and Microsoft-managed keys
B) Deploy SQL Server on Azure Virtual Machines and manage encryption keys locally on the VM
C) Use Azure SQL Database with Always Encrypted and store keys in the application configuration
D) Use Azure SQL Database with TDE and customer-managed keys stored in Azure Key Vault

---

**Q8.** A startup is evaluating Azure cloud services for their new IoT application that will process sensor data. During the initial 6-month pilot, they expect highly variable traffic (ranging from 100 to 50,000 requests per hour). After the pilot, if successful, they will scale to consistent high volume. Their CTO is concerned about upfront costs and wants to understand the financial model. Which cloud benefit is MOST relevant to their pilot phase requirements?

A) High availability ensures the application remains accessible during the variable traffic patterns
B) Consumption-based pricing allows paying only for resources used during each hour of variable demand
C) Geo-redundancy provides disaster recovery capabilities across multiple Azure regions
D) Vertical scalability enables increasing VM size as the application requirements grow

---

**Q9.** An enterprise is running a legacy inventory management system that requires specific hardware configurations, custom kernel modules, and direct access to the host operating system for compliance auditing. The application cannot be containerized or refactored. Which Azure service model provides the necessary level of control?

A) Azure App Service with custom deployment slots for the legacy application
B) Azure Container Instances with privileged container mode enabled
C) Azure Functions with Premium plan for extended execution timeouts
D) Azure Virtual Machines running the required OS with full administrative access

---

**Q10.** A healthcare organization operates clinics in both the United States and the European Union. Due to data residency regulations, patient data from EU clinics must remain in EU datacenters, while US patient data must remain in US datacenters. The organization also maintains some on-premises servers for legacy systems that cannot be migrated. They need a unified management approach across all environments. Which cloud deployment model BEST fits these requirements?

A) Public cloud with multiple Azure regions in US and EU
B) Hybrid cloud combining on-premises infrastructure with Azure public cloud in multiple regions
C) Private cloud deployed separately in US and EU datacenters
D) Community cloud shared with other healthcare organizations in US and EU

---

**Q11.** A company's application currently experiences 2-3 hours of scheduled downtime monthly for updates, resulting in lost revenue. The business requires the application to remain accessible during updates and recover automatically from individual component failures without manual intervention. The company's acceptable data loss window is 1 hour, and they can tolerate up to 4 hours for full recovery after a major datacenter failure. Which two cloud capabilities are MOST critical to achieve these requirements?

A) Elasticity to handle traffic spikes during updates and manageability to simplify the update process
B) Disaster recovery to meet the 4-hour recovery objective and governance to enforce update policies
C) High availability to eliminate scheduled downtime and reliability to enable automatic recovery from component failures
D) Scalability to add resources during updates and predictability to forecast update windows

---

**Q12.** A manufacturing company is deploying a quality control system on Azure. Their compliance officer requires documented proof that Azure datacenters meet ISO 27001 standards, that all administrative actions on their resources are logged for audit, and that they can enforce policies preventing developers from creating resources in non-compliant configurations. In the shared responsibility model, which security and governance aspects are the customer's responsibility?

A) Verifying Azure's ISO 27001 compliance, implementing activity logging, and preventing non-compliant resource configurations
B) Physical datacenter security, enabling audit logging features, and defining governance policies for resource deployment
C) Achieving ISO 27001 certification for Azure datacenters, monitoring administrative actions, and creating compliance policies
D) Obtaining Azure's compliance certifications, configuring Azure Activity Log retention, and implementing Azure Policy to enforce configuration standards

---

**Q13.** A manufacturing company operates globally and needs to deploy Azure resources in a geography where data must remain within specific national boundaries due to legal requirements. The company cannot use standard Azure public cloud regions. Which Azure offering should they use?

A) Azure region pairs in the same geography
B) Azure availability zones within a single region
C) Azure sovereign regions
D) Azure management groups with policy enforcement

---

**Q14.** A development team needs to run a containerized microservices application that requires automatic scaling, load balancing, self-healing, and rolling updates without managing the underlying infrastructure. The team wants built-in monitoring and wants to use Kubernetes. Which Azure service BEST meets these requirements?

A) Azure Container Instances
B) Azure Virtual Machine Scale Sets with Docker
C) Azure Kubernetes Service (AKS)
D) Azure App Service with container support

---

**Q15.** A financial services company needs to connect their on-premises datacenter to Azure with a private, dedicated connection that does NOT traverse the public internet and provides predictable latency and throughput up to 100 Gbps. Which networking service should they implement?

A) Azure ExpressRoute
B) Azure VPN Gateway with Site-to-Site VPN
C) Azure Virtual Network peering
D) Azure Bastion with private endpoints

---

**Q16.** A company stores 500 TB of archived compliance documents that are accessed once per year for audits. They need the lowest possible storage cost and can tolerate several hours of retrieval time. The data must be kept for 10 years. Which Azure Storage solution provides the MOST cost-effective option?

A) Azure Blob Storage Hot tier with LRS redundancy
B) Azure Blob Storage Archive tier
C) Azure Blob Storage Cool tier with GRS redundancy
D) Azure Files Premium tier

---

**Q17.** A healthcare organization requires users to sign in once using their corporate credentials and then access multiple Azure services and SaaS applications without re-entering passwords. Additionally, they want to require an authentication app verification when users sign in from unknown devices. Which combination of Microsoft Entra ID features addresses these requirements?

A) Microsoft Entra External Identities with passwordless authentication
B) Single Sign-On (SSO) combined with Multi-Factor Authentication (MFA)
C) Role-Based Access Control (RBAC) with Conditional Access policies
D) Microsoft Entra Domain Services with Self-Service Password Reset

---

**Q18.** A company is developing an application that needs to process user-uploaded images to detect inappropriate content using AI. They want to use a pre-built Azure AI service without training custom models and need to ensure they follow responsible AI principles including transparency and accountability. Which Azure service should they use and what responsibility framework must they follow?

A) Azure OpenAI Service in Azure AI Foundry with custom content filters
B) Azure Machine Learning with custom-trained moderation models
C) Azure AI Vision with Content Safety API applying Microsoft's Responsible AI Standard
D) Microsoft Copilot with enterprise data protection

---

**Q19.** A healthcare organization requires a solution that uses natural language processing to extract insights from patient feedback forms while ensuring compliance with data residency requirements in Canada. The solution must integrate with existing Azure services and provide pre-built AI models. Which Azure service BEST meets these requirements?

A) Use Azure AI Language service in the Canada Central region with custom text analytics features
B) Deploy Azure OpenAI Service in the Canada Central region with GPT-4 models for text analysis
C) Implement Azure Machine Learning in Canada Central to build custom NLP models from scratch
D) Configure Azure Cognitive Search in Canada East with AI enrichment pipelines

---

**Q20.** A company runs a stateless web application that experiences unpredictable traffic spikes ranging from 10 to 500 concurrent users throughout the day. The application consists of containerized microservices that must scale automatically within seconds and only incur costs during actual request processing. Which compute solution provides the MOST cost-effective approach?

A) Azure Kubernetes Service (AKS) with Horizontal Pod Autoscaler and cluster autoscaler enabled
B) Azure Virtual Machine Scale Sets with custom autoscale rules based on CPU metrics
C) Azure App Service with autoscale configured for HTTP queue length
D) Azure Container Instances with Azure Container Apps for automatic HTTP-based scaling

---

**Q21.** An organization is designing a disaster recovery strategy for a mission-critical SQL database. The database must remain available even if an entire Azure region becomes unavailable, with automatic failover and a Recovery Point Objective (RPO) of less than 5 seconds. Which storage redundancy option meets these requirements?

A) Zone-redundant storage (ZRS) with three synchronous copies across availability zones
B) Geo-redundant storage (GRS) with asynchronous replication to a paired region
C) Locally-redundant storage (LRS) with application-level replication to another region
D) Geo-zone-redundant storage (GZRS) combining ZRS in primary region with GRS to secondary region

---

**Q22.** A financial services company needs to ensure that administrators can only access Azure virtual machines through a secured management network without exposing RDP or SSH ports to the public internet. The solution must support just-in-time access and maintain an audit trail. Which combination of Azure services accomplishes this?

A) Azure Bastion with Microsoft Defender for Cloud just-in-time VM access policies
B) Azure VPN Gateway with Point-to-Site VPN and Network Security Groups blocking internet access
C) Azure ExpressRoute with private peering and Azure Firewall Premium for threat protection
D) Public IP addresses with Conditional Access policies requiring MFA for administrative access

---

**Q23.** A global manufacturing company has 15 subsidiaries, each with its own IT team and budget. The parent company requires centralized visibility of all Azure spending and the ability to enforce that no subsidiary can deploy resources outside their assigned regions (Europe subsidiaries to West Europe, Asia subsidiaries to Southeast Asia, etc.). Which Azure governance structure BEST supports these requirements?

A) Create separate Azure subscriptions for each subsidiary and apply Azure Policy at the subscription scope to restrict allowed regions
B) Implement a management group hierarchy with region-specific Azure Policies inherited by subsidiary subscriptions
C) Use a single subscription with 15 resource groups and apply region restrictions using resource locks on each resource group
D) Deploy Azure Blueprints at the tenant level with region assignments defined in blueprint artifacts

---

**Q24.** A development team is migrating a Python-based machine learning model training pipeline to Azure. The pipeline runs for 2-3 hours once per week to retrain models using 200GB of training data stored in Azure Blob Storage. The team wants to minimize costs and avoid managing infrastructure. Which approach is MOST cost-effective?

A) Deploy the Python application to Azure App Service on a Premium V3 tier plan
B) Create an Azure Container Instance with the training script and run it on-demand using scheduled automation
C) Use Azure Functions with the Premium plan and extended execution timeout configured to 10 hours
D) Provision a Standard_D4s_v3 virtual machine and configure it to start only during training windows

---

**Q25.** A company is deploying Azure AI services for processing customer support tickets using natural language understanding. The solution must ensure data residency in Europe, provide automatic failover if the primary region becomes unavailable, and maintain consistent API endpoints for the application. The company wants to minimize administrative overhead. Which Azure architecture component BEST supports this requirement?

A) Deploy Azure AI services in a single European region and configure multiple resource instances with Traffic Manager for load distribution
B) Create Azure AI services resources in multiple sovereign regions across Europe and manually synchronize configurations
C) Deploy Azure AI services using availability zones within a single European region for high availability
D) Use Azure region pairs by deploying Azure AI services in North Europe with automatic geo-redundant replication to West Europe

---

**Q26.** A financial services company runs a transaction processing application that experiences predictable traffic spikes between 9 AM and 5 PM on weekdays, reaching 200% of baseline capacity. During off-hours and weekends, traffic drops to 20% of baseline. The application is containerized and must maintain sub-second response times during peak hours while minimizing costs during low-traffic periods. Which Azure compute solution BEST meets these requirements?

A) Azure Container Instances with manual scaling based on time schedules
B) Azure Kubernetes Service (AKS) with Horizontal Pod Autoscaler and cluster autoscaler configured based on CPU metrics
C) Azure Virtual Machine Scale Sets running container hosts with scheduled scaling rules
D) Azure App Service with automatic scaling enabled and always-on configured

---

**Q27.** An organization needs to migrate 500 TB of archived medical imaging data from an on-premises storage array to Azure Blob Storage Archive tier. The datacenter has a 1 Gbps internet connection shared with production traffic, and the migration must complete within 2 weeks without impacting normal business operations. Network bandwidth during business hours (8 AM - 6 PM) is limited to 20% of capacity for migration traffic. Which migration approach should the organization use?

A) Order Azure Data Box Heavy, copy data on-premises, and ship the device to Microsoft for bulk upload
B) Use AzCopy with bandwidth throttling configured to 200 Mbps during business hours and full speed during off-hours
C) Configure Azure File Sync with cloud tiering enabled to gradually migrate data over the 2-week period
D) Use Azure Storage Explorer with multiple parallel transfer threads scheduled during off-peak hours only

---

**Q28.** A company is implementing a Zero Trust security model for their Azure environment hosting a custom web application. The application uses Microsoft Entra ID for authentication and stores sensitive customer data. External partners need occasional access to specific application functions but should NOT have permanent access credentials. The security team requires verification of device compliance and geographic location for every access attempt. Which combination of Azure security capabilities implements this Zero Trust requirement?

A) Azure VPN Gateway with point-to-site connections and network security groups restricting access by IP address ranges
B) Role-Based Access Control (RBAC) with custom roles limiting partner permissions and periodic access reviews
C) Microsoft Entra External ID for partner accounts combined with Conditional Access policies requiring compliant devices and location-based restrictions
D) Microsoft Defender for Cloud with just-in-time (JIT) VM access and network security recommendations

---

**Q29.** A healthcare company is deploying Azure OpenAI Service through Azure AI Foundry to analyze patient feedback and generate insights while ensuring compliance with responsible AI principles. The solution must prevent the model from generating medical diagnoses, detect and filter potential personally identifiable information (PII) in user inputs, and maintain an audit trail of all AI-generated content. Which Azure capability is specifically designed to address these responsible AI requirements?

A) Microsoft Defender for Cloud security policies with compliance dashboards for AI workload monitoring
B) Azure Monitor Application Insights with custom telemetry for tracking AI model responses
C) Azure AI Content Safety integrated with Azure OpenAI deployments to detect PII, apply content filtering, and block harmful outputs
D) Microsoft Entra ID Conditional Access policies requiring multi-factor authentication for AI service access

---

**Q30.** A company wants to prevent any user from accidentally deleting a critical resource group containing production databases. The company also needs to allow authorized administrators to update resource configurations within the group when necessary. Which Azure feature should be applied to the resource group?

A) Apply an Azure Policy with the 'Deny' effect to block all delete operations
B) Apply a ReadOnly resource lock to the resource group
C) Apply a CanNotDelete resource lock to the resource group
D) Configure role-based access control (RBAC) to remove delete permissions for all users

---

**Q31.** A development team is using Azure Cloud Shell to manage resources across multiple subscriptions. They need to run a script that creates 50 storage accounts using a declarative approach that can be version-controlled and reused. Which tool combination should they use directly within Cloud Shell?

A) Azure PowerShell with a loop to create each storage account individually
B) Azure CLI with Bicep templates
C) Azure portal's bulk create feature
D) Azure Resource Manager REST API with JSON payloads

---

**Q32.** An organization needs to estimate the cost savings of migrating their on-premises infrastructure to Azure. They want to compare their current datacenter costs including electricity, cooling, hardware depreciation, and IT staff time against Azure's projected costs over 5 years. Which Microsoft tool should they use?

A) Total Cost of Ownership (TCO) Calculator to compare on-premises vs Azure costs
B) Azure Pricing Calculator to model total infrastructure costs
C) Microsoft Cost Management to analyze current spending patterns
D) Azure Advisor cost recommendations to optimize cloud spending

---

**Q33.** A company has deployed resources across 15 different resource groups in Azure. They need to identify which resources belong to the Finance department and generate monthly cost reports grouped by department. The solution should not affect resource functionality or performance. What should they implement?

A) Organize all Finance resources into a dedicated resource group and use Microsoft Cost Management filtering
B) Create a separate Azure subscription for Finance department resources
C) Apply a tag with key 'Department' and value 'Finance' to all Finance resources, then filter cost reports by this tag
D) Use Azure Policy to automatically group resources by department in cost reports

---

**Q34.** An IT administrator receives an alert that a critical Azure service is experiencing an outage affecting their production environment in the East US region. They need to check the current status of Azure services, view the root cause analysis, and subscribe to updates about this specific incident. Which Azure tool should they use?

A) Azure Monitor to query service health logs and create alert rules
B) Azure Service Health to view service issues and planned maintenance
C) Azure Advisor to review service health recommendations
D) Microsoft Cost Management to check if the outage is affecting billing

---

**Q35.** A multinational corporation needs to manage Azure resources, on-premises servers, AWS EC2 instances, and Google Cloud VMs from a single control plane. They want to apply Azure Policy and use Azure Monitor across all these environments. Which Azure service enables this unified management approach?

A) Azure Arc to extend Azure management to hybrid and multi-cloud resources
B) Azure Resource Manager to create a unified resource hierarchy
C) Azure Monitor with multi-cloud connectors
D) Microsoft Defender for Cloud to manage security across clouds

---

**Q36.** A company has deployed 200 Azure VMs across 15 resource groups. The finance team reports that monthly costs have increased by 40% over the past quarter, but they cannot identify which department or project is responsible for the spending. The company needs a solution that allows them to track costs by department without changing existing resource deployments or requiring additional Azure services. What should the company implement?

A) Create separate Azure subscriptions for each department and move resources accordingly
B) Configure Azure Policy to automatically document resource ownership in Azure Monitor logs
C) Deploy Azure Arc to track resource consumption across departments
D) Apply cost allocation tags to existing resources and use Microsoft Cost Management to filter and analyze costs by tag

---

**Q37.** An organization is evaluating whether to migrate their on-premises SQL Server environment to Azure. They need to estimate the total cost of ownership over a 5-year period, including cost savings from decommissioning on-premises hardware, reduced datacenter power consumption, and elimination of software licensing fees. Which tool should they use?

A) Azure Pricing Calculator
B) Microsoft Cost Management
C) Azure Advisor cost recommendations
D) Total Cost of Ownership (TCO) Calculator

---

**Q38.** A company operates Azure resources across multiple regions globally. They need to prevent any user from accidentally deleting a critical Azure Virtual Network that hosts production workloads. The solution must allow authorized administrators to modify the Virtual Network's configuration (such as adding subnets or updating DNS settings) but completely block deletion attempts until the protection is explicitly removed. Which solution meets these requirements?

A) Apply a CanNotDelete resource lock to the Virtual Network
B) Assign Azure Policy with the 'Deny' effect to block Virtual Network deletions
C) Configure Azure role-based access control (RBAC) to remove the delete permission for all users
D) Apply a ReadOnly resource lock to the Virtual Network

---

**Q39.** A financial services company must ensure that all Azure Storage accounts are created with encryption at rest enabled and that blob data is never stored in the Cool or Archive access tiers due to compliance requirements. They need an automated solution that prevents non-compliant storage accounts from being created by any user, even subscription owners. What should they implement?

A) Create an Azure Policy with the 'Deny' effect that blocks creation of storage accounts with disabled encryption or Cool/Archive tiers
B) Configure Azure Advisor to generate alerts when non-compliant storage accounts are detected
C) Use Microsoft Purview to audit storage account configurations and generate compliance reports
D) Apply a CanNotDelete lock to all existing storage accounts

---

**Q40.** A development team has deployed 30 virtual machines across three Azure regions. They receive a notification from Azure Service Health indicating that a planned maintenance event will occur in the East US region in 72 hours, potentially affecting their VMs in that region. The team wants to automate the deployment of identical infrastructure to another region using declarative configuration files that can be version-controlled and reused. Which approach should they use?

A) Use Azure Cloud Shell to write bash scripts that execute Azure CLI commands to recreate the infrastructure
B) Manually configure resources through the Azure portal and document the steps
C) Install Azure PowerShell locally and write imperative scripts to provision resources
D) Deploy the infrastructure using Azure Resource Manager (ARM) templates or Bicep files

---

**Q41.** A company has deployed resources across Azure, AWS, and on-premises VMware environments. They need a unified solution to manage compliance policies, perform security assessments, and apply Azure governance capabilities to all their servers regardless of location. Which Azure service should they implement?

A) Microsoft Purview for unified multi-cloud governance
B) Azure Monitor to collect logs from all environments
C) Microsoft Cost Management to track costs across cloud providers
D) Azure Arc to extend Azure management capabilities to multi-cloud and on-premises resources

---

**Q42.** A company has deployed resources across 15 Azure subscriptions with no consistent naming or organizational structure. The CFO requires monthly cost reports grouped by department (Finance, Engineering, Marketing) and environment (Production, Development). Resources are already deployed and running. Which solution provides the MOST efficient way to meet this requirement?

A) Create a new management group hierarchy, move subscriptions into department-based management groups, then use Azure Cost Management to filter by management group
B) Apply Azure Policy to enforce naming conventions on all new resources, then manually rename existing resources to include department and environment identifiers
C) Create and apply tags for Department and Environment to existing resources, then use Microsoft Cost Management cost analysis with tag filters
D) Deploy Azure Monitor workbooks to query resource metadata and generate custom cost reports by parsing resource names for department indicators

---

**Q43.** An organization's Azure Policy is set to deny the creation of virtual machines in the East US region. A resource lock of type CanNotDelete is applied at the resource group level. An administrator with Owner role at the subscription level attempts to delete a virtual machine in that resource group located in West US. What is the result?

A) The deletion fails because the CanNotDelete lock prevents any delete operations regardless of the administrator's role assignment
B) The deletion succeeds because the Azure Policy only restricts creation in East US, not deletion in West US
C) The deletion succeeds because the Owner role at subscription level overrides resource group-level locks
D) The deletion fails because Azure Policy deny effects apply to both creation and deletion operations

---

**Q44.** A development team needs to provision Azure resources using infrastructure as code. They require the ability to declare resources in a human-readable format, preview changes before deployment, and integrate with existing CI/CD pipelines. The solution must be natively supported by Azure Resource Manager without requiring installation of third-party tools on build agents. Which option BEST meets these requirements?

A) Azure CLI scripts with imperative commands to create resources, stored in the source control repository
B) ARM JSON templates with nested deployments for modularity, deployed via Azure DevOps pipeline tasks
C) Terraform configurations using the AzureRM provider with terraform plan for change preview
D) Bicep templates deployed using the Azure CLI or Azure PowerShell with what-if operation support

---

