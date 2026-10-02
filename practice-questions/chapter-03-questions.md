## Chapter 3: IaaS, PaaS, SaaS and Cloud Service Models — Practice Questions

**Q1.** A company is migrating an on-premises SQL Server database to Azure. The database requires OS-level access for custom monitoring agents and specific Windows Server configurations. The company wants minimal changes to their existing setup. Which solution BEST meets these requirements?

A) SQL Server on Azure Virtual Machines (IaaS)
B) Azure SQL Database with elastic pools for cost optimization
C) Azure SQL Managed Instance with VNet integration
D) Azure Database for PostgreSQL with high availability

<details>
<summary>Answer</summary>

**Correct: A**

SQL Server on Azure VMs (IaaS) provides full OS-level access, allowing custom monitoring agents and Windows Server configurations. This is a classic lift-and-shift scenario where IaaS is appropriate because the customer needs complete control over the operating system and SQL Server instance.

**Why the others are wrong:**
- Azure SQL Database (PaaS) does not provide OS-level access or the ability to install custom monitoring agents at the operating system level
- Azure SQL Managed Instance (PaaS) does not provide OS-level access to the underlying Windows Server, despite being nearly 100% compatible with SQL Server
- Azure Database for PostgreSQL is not SQL Server and would require significant application changes, plus it's also PaaS without OS access

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A startup is developing a new web application and wants to focus entirely on code development without managing infrastructure, operating systems, or runtime environments. They need automatic scaling and built-in load balancing. Which service model should they choose?

A) IaaS - Deploy virtual machines and configure load balancers manually
B) PaaS - Use Azure App Service for web hosting
C) SaaS - Purchase a pre-built web application platform
D) IaaS - Use Azure Virtual Machine Scale Sets with custom configurations

<details>
<summary>Answer</summary>

**Correct: B**

PaaS (Azure App Service) is designed for developers who want to focus on code without managing infrastructure. It provides automatic scaling, built-in load balancing, and eliminates OS/runtime management—perfect for cloud-native development scenarios.

**Why the others are wrong:**
- IaaS with VMs requires managing operating systems, patching, and manual load balancer configuration, which contradicts the requirement to avoid infrastructure management
- SaaS provides pre-built applications for consumption, not a platform for developing custom web applications
- Virtual Machine Scale Sets (IaaS) still require OS management, patching, and configuration even with automatic scaling

</details>

---

**Q3.** In terms of shared responsibility, which security task is the customer's responsibility in ALL three service models (IaaS, PaaS, and SaaS)?

A) Physical network security and datacenter access controls
B) Identity and access management (user accounts and permissions)
C) Operating system patches and security updates
D) Storage infrastructure encryption at rest

<details>
<summary>Answer</summary>

**Correct: B**

Identity and access management (who can access what) is ALWAYS the customer's responsibility across IaaS, PaaS, and SaaS. The customer controls user accounts, permissions, authentication policies, and access rights regardless of service model.

**Why the others are wrong:**
- Physical network security and datacenter access are ALWAYS Microsoft's responsibility in all cloud service models
- Operating system patches are customer's responsibility in IaaS only; Microsoft manages OS patches in PaaS and SaaS
- Storage infrastructure encryption at rest is Microsoft's responsibility in all service models (though customers control encryption keys in some scenarios)

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** A company currently uses Microsoft 365 for email and Office applications. They want to add CRM capabilities without managing any infrastructure or application updates. Which service model and solution should they choose?

A) SaaS - Subscribe to Dynamics 365 Sales
B) IaaS - Deploy Dynamics 365 on Azure Virtual Machines
C) PaaS - Build a custom CRM using Azure App Service and Azure SQL Database
D) IaaS - Use Azure Kubernetes Service to run containerized CRM applications

<details>
<summary>Answer</summary>

**Correct: A**

Dynamics 365 Sales is a SaaS solution that requires zero infrastructure management or application updates—Microsoft handles everything. The customer simply consumes the CRM functionality through a subscription, matching the requirement perfectly.

**Why the others are wrong:**
- Deploying Dynamics 365 on VMs (IaaS) would require managing infrastructure, OS, and application updates, which contradicts the requirements
- Building custom CRM with PaaS requires development effort, ongoing maintenance, and managing the application layer
- Azure Kubernetes Service (IaaS) requires managing container orchestration, infrastructure, and application updates

</details>

---

**Q5.** A financial services company needs to run a legacy application that requires specific kernel modules and custom hardware drivers. The application cannot be modified. Which service model provides the necessary level of control?

A) SaaS - Find a third-party financial application that matches requirements
B) PaaS - Use Azure Container Instances with custom images
C) IaaS - Deploy Azure Virtual Machines with full administrative access
D) PaaS - Use Azure Functions with custom runtime support

<details>
<summary>Answer</summary>

**Correct: C**

IaaS (Azure Virtual Machines) provides complete control over the operating system, allowing installation of specific kernel modules and custom hardware drivers. This level of OS-level control is only available in IaaS.

**Why the others are wrong:**
- SaaS applications are pre-built and consumed as-is; they cannot accommodate legacy applications with specific kernel requirements
- Azure Container Instances (PaaS) does not provide access to kernel modules or hardware drivers of the underlying host OS
- Azure Functions (PaaS) is serverless and does not provide OS-level access to install kernel modules or hardware drivers

</details>

---

**Q6.** A development team wants to deploy a Node.js application but needs to control the exact Node.js version, install custom npm packages globally, and configure specific environment variables at the OS level. They also need SSH access for troubleshooting. Which combination of service model and approach is MOST appropriate?

A) PaaS - Azure App Service with application settings and Kudu console
B) SaaS - Use a third-party Node.js hosting platform
C) PaaS - Azure Container Apps with custom container images
D) IaaS - Azure Virtual Machines with Node.js installed manually

<details>
<summary>Answer</summary>

**Correct: D**

The requirement for SSH access, OS-level environment variables, and global npm package installation indicates the need for full OS control, which only IaaS (Azure Virtual Machines) provides. While PaaS can handle Node.js, it doesn't provide SSH access or OS-level control.

**Why the others are wrong:**
- Azure App Service (PaaS) does not provide SSH access (only limited Kudu/SCM console access) and restricts OS-level configurations to maintain the managed platform
- SaaS platforms provide application consumption only, without the ability to deploy custom Node.js applications or access infrastructure
- Azure Container Apps (PaaS) doesn't provide SSH access to containers for troubleshooting and limits OS-level configurations

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q7.** Which scenario represents the PRIMARY advantage of choosing PaaS over IaaS for application development?

A) Complete control over network topology and routing tables
B) Ability to install custom operating system kernels and drivers
C) Direct access to physical server hardware specifications
D) Automatic handling of OS patching, runtime updates, and infrastructure scaling

<details>
<summary>Answer</summary>

**Correct: D**

The primary advantage of PaaS is abstraction from infrastructure management—Microsoft handles OS patching, runtime updates, and infrastructure scaling automatically. This allows developers to focus on application code rather than infrastructure maintenance.

**Why the others are wrong:**
- Complete control over network topology is an IaaS characteristic, not a PaaS advantage (PaaS abstracts networking details)
- Installing custom OS kernels and drivers requires OS-level access, which is only available in IaaS, not PaaS
- Direct access to physical hardware specifications is not provided in any cloud service model (IaaS, PaaS, or SaaS) as hardware is abstracted

</details>

---

**Q8.** A company is evaluating Azure services for different workloads. They need to understand the shared responsibility boundary. In which service model does the customer have responsibility for patching the operating system?

A) Only in SaaS deployments like Microsoft 365
B) In both IaaS and PaaS but not SaaS
C) Only in IaaS deployments like Azure Virtual Machines
D) In all three service models (IaaS, PaaS, and SaaS)

<details>
<summary>Answer</summary>

**Correct: C**

Operating system patching is the customer's responsibility ONLY in IaaS (e.g., Azure Virtual Machines). In PaaS and SaaS, Microsoft manages the operating system and all patching—customers don't have access to the underlying OS.

**Why the others are wrong:**
- In SaaS (Microsoft 365), Microsoft manages everything including the OS, which customers never see or patch
- In PaaS (like Azure App Service), Microsoft manages and patches the underlying operating system; customers manage only the application layer
- OS patching is never the customer's responsibility in SaaS or PaaS, only in IaaS

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

