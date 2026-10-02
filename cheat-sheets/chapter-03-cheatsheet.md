# IaaS, PaaS, SaaS Cheat Sheet

## Service Model Comparison Table

| Aspect | IaaS | PaaS | SaaS |
|--------|------|------|------|
| **Control Level** | High - OS, network, storage | Medium - Application only | Low - Consumption only |
| **Customer Manages** | OS, runtime, middleware, data, apps | Application code, data | User access, data in app |
| **Provider Manages** | Physical infrastructure, virtualization | OS, runtime, infrastructure | Everything |
| **OS Patching** | Customer responsibility | Provider responsibility | Provider responsibility |
| **Example Services** | Azure VMs, VNets, Storage | App Service, SQL Database, Functions | Microsoft 365, Dynamics 365 |
| **Use Case** | Lift-and-shift, legacy apps, custom OS needs | Cloud-native apps, focus on code | Ready-to-use applications |
| **Scaling** | Manual (VMSS for automation) | Automatic (built-in) | N/A (provider manages) |
| **SSH/RDP Access** | Yes (full access) | No (limited console access) | No |

## Shared Responsibility Matrix

| Responsibility | IaaS | PaaS | SaaS |
|----------------|------|------|------|
| **Data & Access** | Customer | Customer | Customer |
| **Applications** | Customer | Customer | Provider |
| **Runtime** | Customer | Provider | Provider |
| **Operating System** | Customer | Provider | Provider |
| **Virtual Network** | Customer | Shared | Provider |
| **Physical Network** | Provider | Provider | Provider |
| **Physical Hosts** | Provider | Provider | Provider |
| **Datacenter** | Provider | Provider | Provider |

## Exam Decision Tree

**Need OS-level access or custom drivers?** → IaaS (Azure VMs)

**Building new app, want to focus on code?** → PaaS (App Service, Functions)

**Need pre-built business application?** → SaaS (Microsoft 365, Dynamics 365)

**Migrating existing app unchanged?** → IaaS (lift-and-shift)

**Want automatic scaling without infrastructure management?** → PaaS

## IaaS Specifics

**Azure Virtual Machines:**
- Customer manages: OS patching, antivirus, backup configuration
- Choose OS: Windows Server, Linux distributions
- Install any software, custom drivers, kernel modules
- Full administrative (sudo/admin) access

**When to Choose IaaS:**
- Complete control over environment required
- Legacy applications that cannot be modified
- Custom software installation needed
- Specific compliance requirements for OS configuration
- Lift-and-shift migration scenarios

## PaaS Specifics

**Azure App Service:**
- Auto-scaling built-in
- Supports: .NET, Java, Node.js, Python, PHP
- No OS access, Kudu console for limited diagnostics
- Microsoft handles OS patches automatically

**Azure SQL Database:**
- Managed database service (PaaS)
- No OS access, no SQL Server instance control
- Automatic backups, high availability, patching

**When to Choose PaaS:**
- Cloud-native application development
- Reduce operational overhead
- Automatic scaling and load balancing needed
- Focus on business logic, not infrastructure

## SaaS Specifics

**Microsoft 365:**
- Email (Exchange Online), Office apps, Teams
- Customer manages: user licenses, access policies
- Microsoft manages: infrastructure, application, updates

**Dynamics 365:**
- CRM and ERP applications
- Zero infrastructure management
- Subscription-based consumption

**When to Choose SaaS:**
- Need standard business applications
- No customization required beyond configuration
- Want zero infrastructure/application management
- Pay-per-user subscription model acceptable

## Common Exam Traps

**Azure SQL Database vs SQL on VM:**
- SQL Database = PaaS (no OS access)
- SQL on VM = IaaS (full control)
- Exam asks: need to install monitoring agent at OS level? → IaaS

**Identity Management:**
- Customer responsibility in ALL service models
- Even in SaaS, you manage user accounts and permissions

**OS Patching:**
- IaaS only: customer patches OS
- PaaS and SaaS: Microsoft patches OS (customer doesn't see it)

**Physical Security:**
- Provider responsibility in ALL models
- Datacenter access, physical network = always Microsoft

## Quick Memory Aid

**IaaS = Infrastructure as a Service**
- "I" manage the OS and Apps
- Infrastructure provided, I manage the rest

**PaaS = Platform as a Service**
- "P" for Programming focus
- Platform managed, I write code

**SaaS = Software as a Service**
- "S" for Subscribe and use
- Software ready, I just consume
