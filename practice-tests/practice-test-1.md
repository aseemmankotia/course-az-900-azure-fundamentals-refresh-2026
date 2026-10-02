# Practice Test 1: AZ-900 Azure Fundamentals 2026: Complete Exam Preparation

- **Questions:** 44
- **Time limit:** 90 minutes
- **Passing score:** 70%%

> Answers are in `answer-key-1.md`. Track results in `score-tracker.md`.

---

**Q1.** A healthcare organization must ensure that patient data stored in Azure remains within specific geographic boundaries to comply with data residency regulations. The organization also needs the ability to store some non-sensitive analytics data in the most cost-effective region globally. Which cloud deployment model BEST meets these requirements?

A) Public cloud only, using Azure Policy to restrict resource deployment to compliant regions
B) Private cloud to maintain complete control over all data locations
C) Community cloud shared with other healthcare organizations in the same region
D) Hybrid cloud, keeping regulated data on-premises while using public cloud for non-sensitive workloads

---

**Q2.** A startup company is migrating its application to Azure. The application consists of a web frontend, application logic, and a database. The company wants to minimize infrastructure management while retaining full control over the operating system and runtime environment for the application logic tier. Which combination of Azure service models should they use?

A) PaaS for web frontend, IaaS for application logic, PaaS for database
B) IaaS for all three tiers to maintain consistent management
C) PaaS for all three tiers to minimize management overhead
D) SaaS for web frontend, PaaS for application logic, IaaS for database

---

**Q3.** In the Azure shared responsibility model, which security task is ALWAYS the customer's responsibility regardless of whether they use IaaS, PaaS, or SaaS?

A) Physical security of the datacenter infrastructure
B) Managing user access and identity authentication
C) Patching and updating the host operating system
D) Securing the network infrastructure and physical network devices

---

**Q4.** A company experiences predictable traffic patterns with normal baseline usage but occasional traffic spikes that are 10 times the baseline during product launches. They want to optimize costs while maintaining performance. Which Azure cloud benefit BEST addresses this requirement?

A) High availability through Azure Availability Zones
B) Reliability through geo-redundant deployments
C) Elasticity with automatic scaling based on demand
D) Security through Azure DDoS Protection

---

**Q5.** A financial services firm is evaluating Azure and needs to forecast monthly costs accurately for budgeting purposes. The firm plans to run a specific set of virtual machines 24/7 and wants to minimize cost variance. Which Azure pricing characteristic BEST supports this requirement?

A) Consumption-based pricing with pay-as-you-go billing
B) Reserved instances with one-year or three-year commitments
C) Spot pricing for discounted compute capacity
D) Serverless pricing based on execution count and duration

---

**Q6.** A global retail company needs to ensure their Azure-hosted e-commerce platform can handle region-wide outages without service disruption. The platform must automatically failover to another region, and they have a Recovery Time Objective (RTO) of less than 5 minutes. Which cloud benefit does Azure provide to meet this requirement?

A) Scalability through Azure Virtual Machine Scale Sets
B) Manageability through Azure Monitor and Azure Resource Manager
C) Predictability through Azure Service Level Agreements
D) Reliability through multi-region deployments and automatic failover

---

**Q7.** A retail company runs its inventory management system on physical servers in their datacenter. They are migrating to Azure and want to minimize changes to the application code while reducing hardware management overhead. Which cloud service model should they choose?

A) Infrastructure as a Service (IaaS) - deploy the application on Azure Virtual Machines
B) Software as a Service (SaaS) - migrate to Dynamics 365 Supply Chain Management
C) Platform as a Service (PaaS) - rewrite the application using Azure App Service
D) On-premises - keep servers but use Azure for backup only

---

**Q8.** A healthcare organization needs to ensure their Azure-hosted patient records system can automatically handle increased load during peak hours (8 AM - 6 PM) and reduce resources during off-peak hours to control costs. Which cloud benefit directly addresses this requirement?

A) High availability - ensures the system stays online during hardware failures
B) Scalability - allows resources to increase or decrease based on demand
C) Security - protects patient data through encryption and access controls
D) Predictability - provides consistent performance and costs through SLAs

---

**Q9.** In the shared responsibility model for Azure SQL Database (a PaaS service), which security task is Microsoft's responsibility?

A) Configuring firewall rules to restrict database access to specific IP addresses
B) Managing user authentication credentials and role-based access control (RBAC)
C) Patching and updating the underlying SQL Server database engine
D) Encrypting data in transit between the application and the database

---

**Q10.** A manufacturing company needs to run specialized industrial control software that requires direct access to GPU hardware and specific firmware versions. Some workloads must remain on-premises due to regulatory requirements, while other general business applications can move to the cloud. Which cloud deployment model best fits these requirements?

A) Hybrid cloud - keep regulated workloads and specialized hardware on-premises, migrate other workloads to Azure
B) Public cloud only - migrate all workloads to Azure and use specialized VM sizes
C) Private cloud only - build an on-premises cloud infrastructure for all workloads
D) Community cloud - share infrastructure with other manufacturing companies

---

**Q11.** A startup company with unpredictable user growth wants to understand Azure costs. They currently have 10 users but expect to grow to 1,000+ users within 12 months. Which statement accurately describes the consumption-based pricing model in Azure?

A) Pay a fixed monthly fee regardless of actual resource usage, with discounts for annual commitments
B) Pay upfront capital expenditure for reserved capacity, then no ongoing operational costs
C) Pay based on the number of users accessing the application, charged per user per month
D) Pay only for the compute time, storage, and services actually consumed, with costs scaling as usage increases

---

**Q12.** A financial services company is evaluating Azure and needs to understand governance capabilities. They must enforce that all production resources are deployed only in specific regions (East US and West Europe) and must have specific tags for cost allocation. Which cloud benefit enables this requirement?

A) Manageability - using Azure Portal and CLI to deploy resources to allowed regions
B) Reliability - deploying resources across multiple regions for redundancy
C) Governance - using Azure Policy to enforce region restrictions and mandatory tagging
D) Predictability - using Azure Cost Management to forecast spending by region

---

**Q13.** A healthcare organization needs to deploy virtual machines in Azure to comply with US government regulations requiring that customer data remains within US sovereign boundaries and is isolated from commercial Azure regions. Which Azure offering should they use?

A) Deploy VMs in Azure Government regions
B) Deploy VMs in the US East region and enable Azure Private Link
C) Deploy VMs in multiple availability zones within US West region
D) Deploy VMs using Azure Virtual Desktop in a paired region configuration

---

**Q14.** A company runs a web application that experiences predictable traffic spikes every Monday morning from 8 AM to 10 AM, requiring 20 VMs during this period but only 5 VMs the rest of the week. The application must maintain consistent performance during spikes. Which Azure compute solution BEST optimizes cost while meeting this requirement?

A) Deploy a Virtual Machine Scale Set with scheduled scaling rules
B) Deploy 20 VMs in an availability set with manual scaling
C) Deploy Azure Functions with a Consumption plan
D) Deploy 5 VMs with Azure Reserved Instances and manually add 15 VMs during spikes

---

**Q15.** An organization needs to transfer 80 TB of archived data from an on-premises datacenter to Azure Blob Storage. The datacenter has a 100 Mbps internet connection, and the transfer must complete within 2 weeks. Which Azure service should they use?

A) Use AzCopy over the internet connection
B) Use Azure File Sync to synchronize the data
C) Use Azure Storage Explorer with parallel uploads
D) Order Azure Data Box and ship the physical device

---

**Q16.** A development team needs to ensure that only users from the marketing department can access a specific Azure Storage account, and access should be automatically denied if the user is signing in from outside the corporate network. Which Azure identity and access feature should be configured?

A) Configure Azure Role-Based Access Control (RBAC) with the Storage Blob Data Contributor role assigned to marketing users
B) Enable Microsoft Entra Conditional Access with user group and location conditions
C) Configure Multi-Factor Authentication (MFA) for all marketing department users
D) Create a shared access signature (SAS) token with IP address restrictions

---

**Q17.** A company is deploying an Azure OpenAI model in Azure AI Foundry to generate product descriptions for their e-commerce platform. They must ensure the AI does not generate content that includes profanity, violence, or personally identifiable information. Which responsible AI principle and Azure AI capability should they implement?

A) Implement the Fairness principle by using Azure AI Content Safety to filter outputs
B) Implement the Reliability and Safety principle by using Azure AI Content Safety content filters
C) Implement the Privacy and Security principle by enabling Azure Private Link
D) Implement the Accountability principle by configuring Azure Monitor logging

---

**Q18.** An enterprise has deployed resources across 50 Azure subscriptions organized by department. They need to apply a policy that prevents any user from deploying virtual machines in the West Europe region across all subscriptions, while still allowing VM deployments in other regions. What should they configure?

A) Configure network security groups (NSGs) in each subscription to block traffic to West Europe
B) Enable Microsoft Defender for Cloud and create a security recommendation for West Europe
C) Create a management group containing all 50 subscriptions and apply an Azure Policy with a location restriction at the management group scope
D) Create an Azure Blueprints definition with a location allowlist and assign it to each subscription individually

---

**Q19.** A company needs to deploy a microservices-based application with automatic scaling based on CPU usage and the ability to manage container orchestration. The solution must support both Linux and Windows containers and provide built-in load balancing. Which Azure service BEST meets these requirements?

A) Azure Container Instances with manual scaling configuration
B) Azure Virtual Machine Scale Sets with Docker installed
C) Azure App Service for Containers
D) Azure Kubernetes Service (AKS)

---

**Q20.** An organization has deployed critical production workloads in the East US region. They need to ensure business continuity if an entire Azure region becomes unavailable. According to Azure's region pair architecture, which region is automatically paired with East US for data residency and sequential update deployment?

A) Central US
B) West US 2
C) West US
D) North Central US

---

**Q21.** A development team wants to use Azure OpenAI Service to build a chatbot application. They need to ensure the AI model follows responsible AI principles by filtering harmful content and preventing the generation of inappropriate responses. Which Azure feature should they configure?

A) Microsoft Entra Conditional Access policies
B) Azure AI Content Safety integrated with Azure OpenAI
C) Azure DDoS Protection Standard
D) Microsoft Defender for Cloud security recommendations

---

**Q22.** A company needs to migrate 80 TB of historical data from their on-premises datacenter to Azure Blob Storage. The datacenter has limited internet bandwidth (10 Mbps), and the migration must complete within two weeks without impacting business operations. Which Azure service BEST addresses this requirement?

A) AzCopy with incremental sync over the internet
B) Azure Data Box
C) Azure Storage Explorer with parallel transfers
D) Azure File Sync

---

**Q23.** An organization implements a Zero Trust security model for their Azure environment. Users access Azure resources from various locations and devices. Which combination of identity and access features directly supports the Zero Trust principle of 'verify explicitly'?

A) Azure Virtual Network service endpoints with Network Security Groups
B) Microsoft Entra ID with Conditional Access and Multi-Factor Authentication
C) Role-Based Access Control (RBAC) with Azure resource locks
D) Microsoft Defender for Cloud with Just-In-Time VM access

---

**Q24.** A company runs 30 virtual machines across three different Azure subscriptions under a single Azure Active Directory (now Microsoft Entra ID) tenant. They need to apply a consistent tagging policy and enforce cost limits across all VMs regardless of which subscription they belong to. What is the most efficient approach?

A) Create a management group above the three subscriptions and apply Azure Policy at the management group level
B) Configure Azure Blueprints separately for each subscription with identical policies
C) Use Azure Resource Manager templates to deploy tags during VM creation in each subscription
D) Apply tags manually through Azure portal and set budget alerts for each subscription individually

---

**Q25.** A healthcare company is deploying a patient records application that must remain operational even if an entire Azure datacenter fails, but they want to minimize latency for users in the same geographic area. The company also needs automatic failover without manual intervention. Which Azure architectural feature should they implement?

A) Deploy the application across multiple resource groups in the same region
B) Deploy the application to multiple subscriptions in different regions
C) Deploy the application using region pairs with manual failover configuration
D) Deploy the application across multiple availability zones within a single region

---

**Q26.** A development team needs to run a container-based microservices application with automatic scaling, built-in service discovery, and the ability to perform rolling updates with zero downtime. The team wants managed Kubernetes without managing control plane infrastructure. Which Azure compute service BEST meets these requirements?

A) Azure Container Instances with container groups
B) Azure Kubernetes Service (AKS)
C) Azure App Service with custom containers
D) Azure Virtual Machine Scale Sets with Docker installed

---

**Q27.** A company stores 500 TB of compliance data that must be retained for 7 years but is accessed only once per year for audits. Access time of several hours is acceptable, and the company wants to minimize storage costs. Data is currently on-premises and needs to be migrated to Azure. Which combination provides the MOST cost-effective solution?

A) Use Azure Data Box for migration, store in Blob Storage Archive tier
B) Use AzCopy for migration, store in Blob Storage Cool tier
C) Use Azure File Sync for migration, store in Azure Files Premium tier
D) Use Azure Storage Explorer for migration, store in Blob Storage Hot tier with lifecycle management

---

**Q28.** A company wants to enforce a policy where developers can only create Azure resources in West US and East US regions, and all resources must have a 'Department' tag. The policy should apply to all existing and future subscriptions without requiring configuration for each new subscription. Which Azure feature should they use?

A) Create Azure Policy assignments at the management group level
B) Configure RBAC roles with location and tag restrictions at the subscription level
C) Use resource locks on each resource group to prevent changes
D) Set up Conditional Access policies in Microsoft Entra ID

---

**Q29.** A financial services company is implementing an AI-powered customer service chatbot and needs to ensure it follows responsible AI principles. During testing, they discover the chatbot occasionally provides different loan approval guidance to users based on demographic information. Which Azure AI capability should they use to identify and mitigate this issue?

A) Azure OpenAI Service content filtering
B) Microsoft Copilot for customer service automation
C) Azure AI services fairness assessment tools
D) Azure AI Foundry model performance monitoring

---

**Q30.** A company wants to estimate the cost savings of migrating their on-premises infrastructure to Azure. They need to compare their current datacenter costs including electricity, cooling, and hardware maintenance against Azure's pay-as-you-go pricing. Which tool should they use?

A) Azure Pricing Calculator
B) Microsoft Cost Management
C) Azure Total Cost of Ownership (TCO) Calculator
D) Azure Advisor Cost Recommendations

---

**Q31.** An organization needs to ensure that all Azure resources in their subscription are tagged with 'Department' and 'CostCenter' values before they can be created. Users who attempt to create resources without these tags should receive an error. What should they implement?

A) Configure tag inheritance at the resource group level
B) Create an Azure Policy with a Deny effect that requires specific tags
C) Use Azure Advisor recommendations to identify untagged resources
D) Apply tags manually through the Azure Portal after resource creation

---

**Q32.** A company manages Azure resources across multiple subscriptions and needs to view consolidated cost data, set budgets with email alerts when spending reaches 80% of budget, and analyze spending trends by department using tags. Which tool provides these capabilities?

A) Azure Service Health
B) Microsoft Cost Management
C) Azure Monitor with Log Analytics
D) Azure Total Cost of Ownership Calculator

---

**Q33.** An administrator needs to prevent any user from accidentally deleting a critical Azure SQL Database that contains production data. The database must remain modifiable (schema changes, data updates) but deletion must be blocked for all users including subscription owners. What should be configured?

A) Create an Azure Policy with Deny effect for database deletion
B) Apply a ReadOnly resource lock on the SQL Database
C) Apply a CanNotDelete resource lock on the SQL Database
D) Remove delete permissions using Azure RBAC

---

**Q34.** A developer working from a Linux laptop needs to quickly create an Azure storage account and virtual machine using command-line tools without installing any software locally. Which solution allows them to execute Azure CLI commands directly in their web browser?

A) Azure Cloud Shell accessed through the Azure Portal
B) Azure PowerShell installed on their laptop
C) Azure Resource Manager templates deployed via REST API
D) Azure Arc-enabled server management

---

**Q35.** An organization has Azure virtual machines experiencing performance issues during peak hours. They need a service that automatically analyzes their Azure resources and provides personalized recommendations for cost optimization, performance improvement, security hardening, and operational excellence. Which Azure service provides this functionality?

A) Azure Monitor Application Insights
B) Azure Service Health
C) Azure Advisor
D) Microsoft Purview

---

**Q36.** A company needs to estimate the cost savings of migrating their on-premises datacenter to Azure. The estimate must include operational cost differences over a 5-year period, including electricity, cooling, and staff costs. Which tool should they use?

A) Azure Total Cost of Ownership (TCO) Calculator
B) Azure Pricing Calculator
C) Microsoft Cost Management
D) Azure Advisor Cost Recommendations

---

**Q37.** An organization must ensure that all Azure Storage accounts in their subscription are only accessible via HTTPS and block anonymous access. This policy must be enforced automatically for all current and future storage accounts. What should they implement?

A) Azure Resource Locks on each storage account
B) Role-Based Access Control (RBAC) assignments
C) Network Security Groups (NSGs) on storage subnets
D) Azure Policy with deny effect

---

**Q38.** A finance team needs to categorize Azure resources by department and project to track spending for chargeback purposes. The solution must allow filtering costs in reports even if resources are in different resource groups and subscriptions. What should they use?

A) Resource groups with naming conventions
B) Management groups hierarchy
C) Separate subscriptions for each department
D) Azure tags applied to resources

---

**Q39.** A developer needs to create 50 identical virtual machines across three Azure regions using a declarative configuration file that can be version-controlled. Which approach follows Infrastructure as Code (IaC) principles?

A) Write a PowerShell script that calls New-AzVM cmdlet 50 times with different parameters
B) Use Azure CLI in Cloud Shell with a bash loop to create VMs sequentially
C) Use Azure Portal to create the first VM, then use the 'Export template' feature and deploy copies using Azure Resource Manager (ARM) templates
D) Manually create VMs in Azure Portal and document the configuration steps

---

**Q40.** A company receives an alert that an Azure region is experiencing an outage affecting their production application. They need to check if Microsoft has acknowledged the issue and view estimated resolution time. Where should they look?

A) Azure Monitor alerts dashboard
B) Azure Advisor recommendations
C) Microsoft Cost Management alerts
D) Azure Service Health in the Azure Portal

---

**Q41.** An organization manages Azure resources, AWS workloads, and on-premises servers. They need a unified solution to apply Azure Policy and view inventory across all three environments from a single interface. What should they implement?

A) Azure Monitor with multi-cloud agents installed on all servers
B) Microsoft Purview for unified data governance
C) Azure Lighthouse for cross-tenant management
D) Azure Arc to project non-Azure resources into Azure Resource Manager

---

**Q42.** A company is migrating 50 virtual machines from on-premises to Azure. The IT manager needs to estimate the total cost of ownership (TCO) over 3 years, including the cost savings from decommissioning on-premises infrastructure such as datacenter power, cooling, and hardware maintenance. Which Azure tool should the IT manager use?

A) Azure Pricing Calculator
B) Microsoft Cost Management
C) Azure Advisor
D) Azure TCO Calculator

---

**Q43.** A company has tagged all Azure resources with a 'Department' tag to track costs by business unit. The finance team reports that some new resources are being created without the required tag, making cost allocation incomplete. The company wants to automatically prevent any resource creation that does not include the 'Department' tag. What should the company implement?

A) Create a resource lock on the subscription to prevent untagged resource creation
B) Use Azure Monitor alerts to notify administrators when resources are created without tags
C) Implement an Azure Policy with a Deny effect requiring the 'Department' tag on all resources
D) Configure Microsoft Cost Management to automatically tag untagged resources

---

**Q44.** A developer needs to quickly deploy an Azure storage account and configure its firewall rules using command-line tools. The developer is working from a laptop without any Azure tools installed and cannot install software due to corporate security policies. Which option allows the developer to run Azure CLI commands immediately without local installation?

A) Azure Cloud Shell accessed through the Azure portal
B) Azure PowerShell installed via PowerShell Gallery
C) Azure Resource Manager (ARM) template deployment
D) Azure Arc connected to the local laptop

---

