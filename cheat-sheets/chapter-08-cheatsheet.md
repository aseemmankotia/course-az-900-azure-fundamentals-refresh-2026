# Azure Governance, Monitoring, and Management Tools Cheat Sheet

## Governance Triad (Most Tested)

| Tool | Purpose | Use Case | Exam Keyword |
|------|---------|----------|-------------|
| **Azure Policy** | Enforce configuration standards | "All storage must have encryption" | Compliance, standards, "must have" |
| **RBAC** | Control who can do what | "Bob can create VMs, Alice cannot" | Permissions, access control |
| **Resource Locks** | Prevent changes/deletion | "Don't delete this production DB" | Prevent accidents, immutability |

**Key Distinction**: Policy = WHAT resources can be, RBAC = WHO can act, Locks = PREVENT changes

## Resource Locks

| Lock Type | Prevents Deletion | Prevents Modification |
|-----------|------------------|----------------------|
| **CanNotDelete** | ✅ Yes | ❌ No |
| **ReadOnly** | ✅ Yes | ✅ Yes |

**Critical**: Locks override ALL permissions, even Owner role. To delete locked resource, must remove lock first.

## Monitoring Triad

| Service | Focus | Key Capability | Exam Scenario |
|---------|-------|----------------|---------------|
| **Azure Advisor** | Recommendations | Personalized best practices (Cost, Security, Reliability, Performance, Operational Excellence) | "Reduce costs", "optimize performance" |
| **Azure Monitor** | Metrics & Logs | Collects telemetry, alerts, dashboards; includes Log Analytics & Application Insights | "Track CPU usage", "query logs" |
| **Azure Service Health** | Platform Status | Azure outages, planned maintenance, health advisories for YOUR resources | "Is Azure down?", "maintenance notification" |

**Exam Tip**: Advisor = proactive recommendations, Monitor = reactive metrics/logs, Service Health = Azure platform status

## Application Insights (Part of Azure Monitor)

- **Purpose**: Application Performance Monitoring (APM)
- **Capabilities**: Distributed tracing, dependency tracking, anomaly detection, telemetry
- **Use Case**: "Track request flow through microservices", "identify slow database queries"

## Data Governance

**Microsoft Purview**:
- Unified data governance across Azure, multi-cloud, on-premises
- Discovers, classifies, catalogs data
- Automated scanning, sensitivity labeling, compliance reports
- **Exam Scenario**: "Classify sensitive data across SQL Database, Storage, and on-premises SQL"

## Management Tools

| Tool | Type | Key Feature |
|------|------|-------------|
| **Azure Portal** | Web UI | Browser-based visual interface |
| **Azure CLI** | Command-line | Cross-platform, bash-style syntax |
| **Azure PowerShell** | Command-line | Windows-focused cmdlets |
| **Cloud Shell** | Managed shell | Browser-based, pre-installed CLI + PowerShell, 5GB free storage |

## Infrastructure as Code (IaC)

| Technology | Format | Syntax Type | Relationship |
|------------|--------|-------------|-------------|
| **ARM Templates** | JSON | Declarative | Azure-native IaC |
| **Bicep** | .bicep | Declarative | Compiles to ARM, simpler syntax |

**Declarative**: Define WHAT you want, Azure figures out HOW  
**Idempotent**: Can run multiple times safely, reaches desired state

**Exam Tip**: Bicep is recommended over raw ARM JSON; both deploy via Azure Resource Manager

## Azure Arc

- **Purpose**: Manage non-Azure resources using Azure tools
- **Capability**: Projects on-premises, AWS, GCP, other clouds into Azure Resource Manager
- **Enables**: Azure Policy, RBAC, tags, monitoring on hybrid/multi-cloud resources
- **Exam Scenario**: "Apply Azure Policy to AWS EC2 instances"

## Azure Policy Effects (Common)

| Effect | Behavior |
|--------|----------|
| **Deny** | Blocks non-compliant resource creation |
| **Audit** | Logs non-compliance, allows creation |
| **DeployIfNotExists** | Auto-deploys missing resources (e.g., diagnostic settings) |
| **Append** | Adds properties to resources (e.g., tags) |

## Log Analytics

- **Role**: Central log repository for Azure Monitor
- **Query Language**: KQL (Kusto Query Language)
- **Default Retention**: 30 days (configurable)
- **Use Case**: "Query logs across multiple VMs and resources"

## Quick Decision Tree

**"Enforce all VMs must have backup"** → Azure Policy  
**"Prevent deleting production database"** → CanNotDelete Lock  
**"John can read but not create VMs"** → RBAC (Reader role)  
**"Get cost-saving recommendations"** → Azure Advisor  
**"Track request latency in app"** → Application Insights  
**"Is Azure having an outage?"** → Azure Service Health  
**"Deploy 100 VMs identically"** → ARM/Bicep template  
**"Manage on-prem servers with Azure Policy"** → Azure Arc  
**"Classify sensitive data across data estate"** → Microsoft Purview  

## Common Exam Traps

1. **Policy vs RBAC**: Policy enforces configuration, RBAC controls access. Can't use RBAC to enforce "must have encryption."
2. **ReadOnly vs CanNotDelete**: ReadOnly prevents ALL changes; CanNotDelete allows modifications.
3. **Advisor vs Monitor**: Advisor gives recommendations; Monitor collects metrics. Advisor doesn't alert on high CPU.
4. **Service Health vs Monitor**: Service Health = Azure platform issues; Monitor = your resource metrics.
5. **Arc doesn't migrate**: Azure Arc manages resources where they are; doesn't move workloads to Azure.
