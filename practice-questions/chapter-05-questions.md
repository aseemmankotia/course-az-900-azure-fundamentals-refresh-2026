## Chapter 5: Azure Compute, Networking, and Storage Services — Practice Questions

**Q1.** A company runs a web application that experiences unpredictable traffic spikes during business hours (9 AM - 5 PM) but has minimal traffic at night. The application must scale automatically and the company wants to minimize costs. Which compute solution BEST meets these requirements?

A) Azure Virtual Machines with manual scaling
B) Azure App Service with autoscaling enabled
C) Azure Container Instances running continuously
D) Azure Virtual Desktop for application hosting

<details>
<summary>Answer</summary>

**Correct: B**

Azure App Service is PaaS with built-in autoscaling that automatically adds/removes instances based on metrics like CPU or HTTP requests. It scales down during low-traffic periods to minimize costs and scales up automatically during spikes. Perfect for web apps with variable traffic patterns.

**Why the others are wrong:**
- Manual scaling requires human intervention and won't respond quickly to unpredictable spikes. Also requires managing OS patches and updates.
- Container Instances running continuously means paying for compute even during low-traffic periods. ACI is better for burst/batch workloads, not continuous web apps.
- Azure Virtual Desktop is for desktop virtualization (remote desktops), not for hosting web applications. Wrong service entirely.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A financial services company needs to store 500TB of audit logs that must be retained for 7 years for compliance. The logs are rarely accessed (less than once per year) but must be available within 15 hours if requested by auditors. Which Azure Storage configuration minimizes cost while meeting requirements?

A) Archive tier with LRS redundancy
B) Hot tier with LRS redundancy
C) Cool tier with GRS redundancy
D) Archive tier with GRS redundancy

<details>
<summary>Answer</summary>

**Correct: A**

Archive tier is the cheapest storage option ($0.00099/GB vs $0.018 for Hot) and designed for data accessed less than once per year. Rehydration takes up to 15 hours (meets the 15-hour requirement). LRS (3 copies in one datacenter) is sufficient since financial compliance typically requires availability, not geo-redundancy, and LRS costs less than GRS.

**Why the others are wrong:**
- Hot tier costs 18x more than Archive ($0.018 vs $0.00099/GB). Wasting money for data accessed less than once per year.
- Cool tier is for data accessed at least monthly. Still costs 10x more than Archive. GRS adds unnecessary cost for geo-redundancy when not required.
- GRS (geo-redundant) adds cost by replicating to a second region. Question doesn't mention disaster recovery requirement, only compliance retention. LRS meets availability needs at lower cost.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q3.** A company operates manufacturing plants in three Azure regions (East US, West Europe, Southeast Asia). Each plant must communicate with the others over low-latency private connections without traffic traversing the public internet. The connection must support bandwidths up to 10 Gbps. Which solution meets these requirements?

A) Site-to-Site VPN Gateway in each region with encryption
B) Virtual network peering between all three regions
C) Azure ExpressRoute with Global Reach enabled
D) Azure DNS private zones with VPN connections

<details>
<summary>Answer</summary>

**Correct: C**

ExpressRoute provides private connections (doesn't use public internet) with up to 100 Gbps bandwidth (meets 10 Gbps requirement). ExpressRoute Global Reach allows on-premises locations in different regions to communicate with each other through Microsoft's backbone network, providing low-latency cross-region connectivity.

**Why the others are wrong:**
- VPN Gateway connections traverse the public internet (encrypted but still internet-based). Maximum bandwidth is 10 Gbps for VpnGw5 SKU but latency is higher than private connections. Doesn't meet 'without traversing public internet' requirement.
- VNet peering connects virtual networks, not on-premises manufacturing plants to Azure. The question implies physical plant locations need connectivity. VNet peering alone doesn't connect on-premises sites.
- Azure DNS is for name resolution, not network connectivity. VPN connections still use the public internet. This combines two services that don't solve the core requirement.

</details>

---

**Q4.** A development team needs to run a batch processing job that executes once per day at 2 AM, processes data for 10 minutes, then terminates. The job requires 4 CPU cores and 8GB RAM. Which compute option minimizes cost?

A) Azure Virtual Machine with B-series burstable instance running 24/7
B) Azure Functions with Premium plan
C) Azure Container Instances started via scheduled Azure Logic App
D) Azure Kubernetes Service with one-node cluster

<details>
<summary>Answer</summary>

**Correct: C**

Azure Container Instances charges only for compute time used (per-second billing). Starting ACI via Logic App on a schedule means paying only for ~10 minutes per day. ACI supports up to 4 CPU cores and 16GB RAM (meets 4 core/8GB requirement). Logic App scheduling is free tier eligible.

**Why the others are wrong:**
- Running a VM 24/7 means paying for 23 hours and 50 minutes of idle time every day. Even B-series (cheapest) costs more than 10 minutes of ACI usage.
- Premium plan (required for scheduled execution without HTTP trigger) has minimum charge even when not running. Consumption plan can't be scheduled directly without HTTP trigger. More expensive than ACI for batch jobs.
- AKS requires paying for at least one node running 24/7 to host the cluster control plane and worker node. Massive overkill for a 10-minute daily job. ACI is simpler and cheaper.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q5.** A company's Azure virtual network in East US (10.1.0.0/16) needs to connect with another virtual network in West US (10.2.0.0/16) so that VMs in both networks can communicate using private IP addresses. The connection must be encrypted and support up to 10 Gbps bandwidth. Which is the MOST cost-effective solution?

A) VPN Gateway connections between the two VNets
B) ExpressRoute circuit connecting both regions
C) Global VNet peering between the two VNets
D) Azure Firewall with network rules allowing cross-region traffic

<details>
<summary>Answer</summary>

**Correct: C**

Global VNet peering (peering across regions) allows VMs to communicate using private IPs, encrypts traffic over Microsoft backbone network, and supports high bandwidth (no specific limit like VPN Gateway). Pricing is only for data transfer ($0.035/GB). No gateway resources needed. Most cost-effective for VNet-to-VNet connectivity.

**Why the others are wrong:**
- VPN Gateway requires deploying and paying for gateway resources in both VNets ($0.04-$0.50/hour per gateway depending on SKU). Also charges for data transfer. More expensive than VNet peering for VNet-to-VNet scenarios.
- ExpressRoute is for on-premises to Azure connections, not VNet-to-VNet. Requires physical circuit installation and monthly circuit fees ($50-$10,000+/month). Massive overkill and most expensive option.
- Azure Firewall doesn't create connectivity between VNets. It's for filtering traffic, not establishing connections. VNets must already be connected (via peering or VPN) for Firewall rules to apply. Doesn't solve the requirement.

</details>

---

**Q6.** A startup needs to deploy a scalable microservices application with 8 different services, each needing independent scaling, health monitoring, and automated rollback capabilities. The team has Kubernetes expertise. Which Azure compute service is MOST appropriate?

A) Azure Virtual Machine Scale Sets with custom load balancing
B) Azure Container Instances with Azure Load Balancer
C) Azure App Service with deployment slots for each microservice
D) Azure Kubernetes Service (AKS) with managed node pools

<details>
<summary>Answer</summary>

**Correct: D**

AKS is designed for orchestrating containerized microservices with Kubernetes. Provides independent scaling per service (Horizontal Pod Autoscaler), built-in health monitoring (liveness/readiness probes), and automated rollback (Kubernetes deployments). Team's Kubernetes expertise makes AKS the natural choice. Managed control plane reduces operational overhead.

**Why the others are wrong:**
- VM Scale Sets require manual configuration of container orchestration, service discovery, health checks, and rollback logic. No built-in microservices orchestration. Team would need to build what AKS provides out-of-the-box.
- ACI doesn't provide service orchestration, inter-service networking, or rollback capabilities. Each container instance is independent. No built-in load balancing between container groups. Not designed for complex microservices architectures.
- App Service is PaaS for web apps, not microservices orchestration. Would need 8 separate App Service instances (one per microservice). Deployment slots are for staging/production, not microservices architecture. More expensive and complex than AKS for this use case.

</details>

---

**Q7.** A global e-commerce company stores product images in Azure Blob Storage. The images must survive both datacenter failures within a region AND an entire region outage. Read access must remain available during a regional outage. Which storage redundancy option meets these requirements at the lowest cost?

A) Geo-zone-redundant storage (GZRS) with read access enabled
B) Locally-redundant storage (LRS) with manual replication scripts
C) Zone-redundant storage (ZRS) in the primary region
D) Geo-redundant storage (GRS) with read access enabled

<details>
<summary>Answer</summary>

**Correct: A**

GZRS with read access (RA-GZRS) provides zone redundancy in the primary region (survives datacenter failures) AND geo-replication to secondary region (survives region outage). Read access to secondary region during primary region outage meets the 'read access during regional outage' requirement. Only option that meets both requirements.

**Why the others are wrong:**
- LRS only replicates within one datacenter. Doesn't survive datacenter or region failures. Manual scripts don't provide automatic failover or read access during outage.
- ZRS survives datacenter failures within a region but doesn't replicate to another region. If the entire region fails, data is unavailable. Doesn't meet 'survive region outage' requirement.
- GRS replicates to secondary region but ZRS (not GRS) provides zone redundancy in primary region. GRS uses LRS in primary region, so a datacenter failure (but not full region failure) could cause brief unavailability. Doesn't meet 'datacenter failure' requirement as robustly as GZRS.

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** A company runs a legacy application that requires Windows Server 2016 with specific registry configurations and third-party software installed. 200 remote employees need access to this application from personal devices. Which Azure service is MOST appropriate?

A) Azure Virtual Machines accessed via Azure Bastion
B) Azure Virtual Desktop with personal desktop assignment
C) Azure App Service with Windows container
D) Azure Functions running Windows-based code

<details>
<summary>Answer</summary>

**Correct: B**

Azure Virtual Desktop is designed for remote desktop scenarios. Supports Windows Server 2016, allows full OS customization (registry, third-party software), and provides personal desktop assignment so each user gets their own persistent VM. Optimized for remote access from any device. Built-in security and compliance features for remote work.

**Why the others are wrong:**
- While VMs could run the application, giving 200 employees direct VM access via Bastion is not designed for end-user desktop scenarios. Bastion is for admin access, not end-user application delivery. Licensing and management would be complex.
- App Service doesn't support legacy applications requiring specific OS configurations and registry changes. Windows containers in App Service are for web apps, not full desktop applications with GUI and third-party dependencies.
- Azure Functions is for serverless code execution, not running interactive desktop applications with GUI. Can't host a legacy application that users interact with. Wrong service category entirely.

</details>

---

