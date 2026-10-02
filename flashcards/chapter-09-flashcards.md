## Chapter 9: AZ-900 Exam Simulation and Test-Taking Strategy — Flashcards

| # | Front (Question) | Back (Answer) |
|---|-----------------|---------------|
| 1 | AZ-900 exam duration and question count? | 45 minutes active exam time, 40-60 questions. Exam tip: ~1 minute per question average. Flag difficult questions, return later if time allows. |
| 2 | What does 'BEST' mean in exam questions? | Multiple answers may work, but one is optimal based on: cost-effectiveness, least admin effort, or meeting all requirements. Exam tip: Eliminate answers that don't meet ALL stated requirements first. |
| 3 | IaaS vs PaaS - who manages the OS? | IaaS: YOU manage OS (VMs, full control). PaaS: MICROSOFT manages OS (App Service, SQL Database, no OS access). Exam tip: 'OS-level access' or 'custom agents' = IaaS required. |
| 4 | Azure Pricing Calculator vs TCO Calculator? | Pricing Calculator: estimates Azure costs only. TCO Calculator: compares on-premises costs vs Azure over time (includes power, cooling, labor). Exam tip: 'migration comparison' = TCO Calculator. |
| 5 | Availability Zones vs Availability Sets - SLA difference? | Availability Zones: 99.99% SLA, protects against datacenter failures. Availability Sets: 99.95% SLA, protects against rack failures only. Exam tip: 'datacenter maintenance' = need Zones. |
| 6 | What keyword indicates cost optimization questions? | 'MOST cost-effective', 'minimize costs', 'lowest price'. Look for: Reserved Instances (up to 72% savings), right-sizing, hybrid licensing. Exam tip: 'predictable workload' often = Reserved Instances. |
| 7 | What keyword indicates simplified management questions? | 'LEAST administrative effort', 'minimize operational overhead', 'simplest solution'. Prefer: PaaS over IaaS, managed services over self-managed. Exam tip: manual processes = wrong answer. |
| 8 | Resource locks: CanNotDelete vs ReadOnly? | CanNotDelete: prevents deletion, allows modifications. ReadOnly: prevents deletion AND modifications. Exam tip: ReadOnly blocks legitimate updates - use carefully. |
| 9 | Azure regions vs Azure Availability Zones? | Region: geographic area with multiple datacenters. Availability Zone: isolated datacenter(s) WITHIN a region (minimum 3 zones per region). Exam tip: Zones = better SLA than single region deployment. |
| 10 | Microsoft Defender for Cloud vs Azure Policy? | Defender for Cloud: unified security management, compliance dashboard, threat protection. Azure Policy: enforce organizational standards, resource compliance. Exam tip: 'security posture' = Defender. |
| 11 | Azure RBAC - what does Contributor role allow? | Create/manage all resource types but CANNOT grant access to others (no permission management). Reader: view only. Owner: full control including access grants. Exam tip: 'prevent deletion' = Reader role. |
| 12 | Spot VMs pricing and availability? | Up to 90% discount vs Pay-As-You-Go BUT can be evicted anytime with 30-second notice. Exam tip: NEVER use Spot VMs for production workloads requiring guaranteed availability. |
