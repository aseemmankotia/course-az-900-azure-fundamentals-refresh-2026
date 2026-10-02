# Azure Compute, Networking, and Storage — AZ-900 Exam Cheat Sheet

## Compute Services Comparison

| Service | Best For | Exam Keywords | Scaling | Price Model |
|---------|----------|---------------|---------|-------------|
| **Virtual Machines** | Full OS control, legacy apps | "custom software", "specific OS version" | Manual or VMSS | Per hour (VM size) |
| **VM Scale Sets** | Identical VMs, autoscaling | "autoscale identical VMs", "load balanced" | Automatic | Per VM + load balancer |
| **Azure Virtual Desktop** | Remote desktops, 200+ users | "remote access", "virtual desktop", "personal/pooled" | Auto (pooled mode) | VMs + storage + network |
| **Container Instances** | Simple containers, batch jobs | "simplest container", "no orchestration", "burst workload" | Manual | Per-second (vCPU + memory) |
| **Azure Kubernetes Service** | Microservices, complex apps | "Kubernetes", "orchestration", "microservices" | Auto (HPA) | Nodes (VMs) only, control plane free |
| **Azure Functions** | Event-driven, sporadic | "event-driven", "pay per execution", "serverless" | Automatic | Consumption: per execution; Premium: per hour |
| **App Service** | Web apps, APIs, always-on | "PaaS web hosting", "continuous", "deployment slots" | Automatic | Per App Service Plan (hourly) |

## When to Use What (Exam Decision Tree)

**Need full OS control or specific software?** → VM  
**Identical VMs that autoscale?** → VM Scale Sets  
**Remote desktop for employees?** → Azure Virtual Desktop  
**Simple container, no orchestration?** → Container Instances  
**Microservices with Kubernetes?** → AKS  
**Code runs on events, <10 min?** → Functions (Consumption)  
**Web app, always-on, HTTP traffic?** → App Service  

## Networking Essentials

| Concept | Purpose | Exam Note |
|---------|---------|----------|
| **Virtual Network (VNet)** | Isolated network in Azure | Address space: 10.0.0.0/16 (up to /8) |
| **Subnet** | Segment VNet for resources | First 5 IPs reserved by Azure |
| **VNet Peering** | Connect VNets privately | Regional or Global; no bandwidth limit |
| **VPN Gateway** | Encrypted connection over internet | Up to 10 Gbps; Site-to-Site or Point-to-Site |
| **ExpressRoute** | Private WAN connection (not internet) | Up to 100 Gbps; predictable latency |
| **Azure DNS** | Host DNS domains in Azure | Public zones: internet-facing; Private: VNet only |

### VPN Gateway vs ExpressRoute

| Feature | VPN Gateway | ExpressRoute |
|---------|-------------|-------------|
| **Connection** | Public internet (encrypted) | Private connection (Microsoft backbone) |
| **Bandwidth** | Up to 10 Gbps | Up to 100 Gbps |
| **Latency** | Variable (internet-dependent) | Predictable, low latency |
| **Setup Time** | Minutes to hours | Weeks to months (physical circuit) |
| **Cost** | $0.04-$0.50/hour | $50-$10,000+/month |
| **Exam Trigger Words** | "encrypted", "quick setup", "budget" | "private", "predictable latency", "hybrid", "compliance" |

## Storage Services

| Service | Use Case | Max Size | Access Method |
|---------|----------|----------|---------------|
| **Blob Storage** | Unstructured data (images, videos, backups) | 190.7 TB per blob | REST API, SDKs |
| **File Storage** | SMB file shares for VMs/apps | 100 TB per share | SMB 3.0, NFS 4.1 |
| **Queue Storage** | Message queue for app communication | Unlimited messages | REST API, SDKs |
| **Table Storage** | NoSQL key-value store | Petabytes | REST API, SDKs |

### Blob Storage Tiers

| Tier | Access Frequency | Cost/GB | Min Duration | Rehydration Time | Exam Scenario |
|------|------------------|---------|--------------|------------------|---------------|
| **Hot** | Daily/frequent | $0.018 | None | N/A | Active data, frequently accessed |
| **Cool** | Monthly | $0.010 | 30 days | N/A | Backups, accessed monthly |
| **Archive** | <1x per year | $0.00099 | 180 days | Up to 15 hours | Compliance logs, long-term retention |

**Early deletion fee:** Delete before min duration = charged for full min duration

## Storage Redundancy Options

| Option | Copies | Location | Survives | Cost | Exam Keyword |
|--------|--------|----------|----------|------|-------------|
| **LRS** | 3 | 1 datacenter | Disk/rack failure | Lowest | "local redundancy only" |
| **ZRS** | 3 | 3 zones in region | Datacenter failure | Low | "zone failure" |
| **GRS** | 6 | Primary region (3 local) + secondary region (3 local) | Region failure | Medium | "region outage" |
| **GZRS** | 6 | Primary (3 zones) + secondary (3 local) | Zone + region failure | Highest | "zone AND region" |
| **RA-GRS** | 6 (same as GRS) | Same as GRS, but secondary is readable | Region failure + read during outage | Medium+ | "read access during outage" |
| **RA-GZRS** | 6 (same as GZRS) | Same as GZRS, but secondary is readable | Zone + region + read during outage | Highest+ | "zone AND region + read access" |

**Exam Pattern:** Match failure scenario to redundancy level  
- Datacenter failure → ZRS minimum  
- Region outage → GRS/GZRS  
- Read during primary region outage → RA-GRS/RA-GZRS  
- Zone + region protection → GZRS/RA-GZRS

## Exam Traps & Gotchas

1. **Archive tier rehydration:** Up to 15 hours (not instant). Must rehydrate before accessing.
2. **Functions Consumption plan:** 10-minute max execution (5 min default). Premium plan = no timeout but costs more.
3. **VNet peering is NOT transitive:** If VNet A peers with B, and B peers with C, A cannot reach C without direct peering.
4. **VM Scale Sets vs Availability Sets:** Scale Sets = autoscaling. Availability Sets = just high availability, manual scaling.
5. **ExpressRoute does NOT encrypt by default:** Use MACsec or VPN over ExpressRoute for encryption.
6. **Azure Virtual Desktop:** You pay for VMs/storage/network, not the AVD service itself.
7. **GRS secondary region:** NOT readable unless you have RA-GRS (Read-Access GRS).
8. **Cool/Archive early deletion:** Delete before 30 days (Cool) or 180 days (Archive) = charged for full minimum duration.
