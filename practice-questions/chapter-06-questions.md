## Chapter 6: Azure Identity, Security, and AI Services (2026 Update) — Practice Questions

**Q1.** A company requires employees to authenticate using their corporate credentials across Microsoft 365, Azure Portal, and third-party SaaS applications without entering credentials multiple times. The solution must minimize password-related security risks. Which authentication method BEST meets these requirements?

A) Configure single sign-on (SSO) with Microsoft Entra ID
B) Implement multi-factor authentication (MFA) for all applications
C) Use Azure AD B2C for external identity management
D) Deploy passwordless authentication with FIDO2 security keys

<details>
<summary>Answer</summary>

**Correct: A**

Single sign-on (SSO) with Microsoft Entra ID allows users to authenticate once and access multiple applications without re-entering credentials. This directly addresses the requirement for authentication across multiple services without repeated logins while using corporate credentials.

**Why the others are wrong:**
- MFA enhances security but doesn't eliminate multiple login prompts across applications - users still need to authenticate separately for each app
- Azure AD B2C is for customer-facing applications (external consumers), not for employee authentication across corporate applications
- Passwordless authentication improves security but doesn't inherently provide single sign-on across multiple applications - SSO configuration is still required

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q2.** A financial services company needs to ensure that users accessing Azure resources from unrecognized devices or locations are required to provide additional verification. Access from corporate networks should proceed normally. Which Microsoft Entra ID feature should be configured?

A) Conditional Access policies
B) Role-based access control (RBAC)
C) Azure Policy
D) Resource locks

<details>
<summary>Answer</summary>

**Correct: A**

Conditional Access policies evaluate signals like location, device state, and risk level to enforce access controls dynamically. They can require MFA or block access based on these conditions while allowing normal access from trusted locations.

**Why the others are wrong:**
- RBAC controls what users can do with resources (permissions) but doesn't evaluate authentication conditions like location or device state
- Azure Policy enforces organizational standards and compliance on resource configurations, not authentication requirements based on access conditions
- Resource locks prevent accidental deletion or modification of resources, completely unrelated to authentication or access conditions

</details>

---

**Q3.** A company has deployed Azure resources across multiple subscriptions. The security team needs to ensure developers cannot create virtual machines larger than Standard_D4s_v3, but IT administrators should have no restrictions. Developers already have Contributor role assigned. What is the MOST appropriate solution?

A) Remove Contributor role from developers and create a custom RBAC role that excludes large VM creation
B) Implement an Azure Policy that denies creation of VMs larger than Standard_D4s_v3 and exempt IT administrators
C) Configure resource locks on all existing VMs to prevent changes
D) Use Conditional Access policies to restrict VM size selections

<details>
<summary>Answer</summary>

**Correct: B**

Azure Policy enforces compliance and organizational standards across resources. A Deny policy can prevent creation of oversized VMs while policy exemptions allow IT administrators to bypass the restriction. This enforces compliance without changing RBAC assignments.

**Why the others are wrong:**
- Custom RBAC roles control permissions but cannot enforce specific configuration requirements like VM sizes - RBAC is about who can do what, not what configurations are allowed
- Resource locks prevent deletion or modification of existing resources but don't control creation of new resources or enforce configuration standards
- Conditional Access policies control authentication and user access conditions, not Azure resource configuration or compliance requirements

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q4.** An e-commerce company wants to allow customers to sign in to their web application using their existing Google or Facebook accounts without creating new credentials. Which Azure service should they implement?

A) Microsoft Entra ID with B2B (Business-to-Business)
B) Microsoft Entra ID with B2C (Business-to-Consumer)
C) Microsoft Entra ID with SSO configuration
D) Azure AD Domain Services

<details>
<summary>Answer</summary>

**Correct: B**

Azure AD B2C (Business-to-Consumer) is specifically designed for customer-facing applications and supports social identity providers like Google, Facebook, and Microsoft accounts. It allows customers to use existing credentials from these providers.

**Why the others are wrong:**
- B2B is for collaboration with external partner organizations (other businesses), not for customer authentication with social identity providers
- SSO enables authentication across multiple applications but doesn't inherently provide integration with social identity providers like Google or Facebook
- Azure AD Domain Services provides managed domain services for lift-and-shift scenarios, not social identity provider integration for customer applications

</details>

---

**Q5.** A company is implementing Zero Trust security principles in Azure. Which statement BEST describes the Zero Trust approach?

A) Trust all traffic within the corporate network perimeter and verify traffic from external sources
B) Deploy multiple layers of security controls and rely on network segmentation as primary defense
C) Implement strong perimeter security with firewalls and VPNs to protect internal resources
D) Verify explicitly, use least privilege access, and assume breach for all access requests

<details>
<summary>Answer</summary>

**Correct: D**

Zero Trust operates on three core principles: verify explicitly (always authenticate and authorize), use least privilege access (grant minimum necessary permissions), and assume breach (minimize blast radius and verify end-to-end encryption). This approach never trusts, always verifies, regardless of network location.

**Why the others are wrong:**
- This describes traditional perimeter-based security model, which Zero Trust explicitly rejects - Zero Trust assumes no implicit trust even within the network perimeter
- This describes defense-in-depth strategy (layered security) which is complementary but different from Zero Trust - defense-in-depth focuses on multiple security layers while Zero Trust focuses on verification and least privilege
- This describes traditional perimeter security model that assumes internal traffic is trusted - Zero Trust assumes no location is trusted and requires verification for all access

</details>

---

**Q6.** A development team needs to integrate natural language processing capabilities into their customer service application to analyze sentiment and extract key phrases from customer feedback. Which Azure AI service is MOST appropriate for this scenario?

A) Azure OpenAI Service with GPT-4 models
B) Azure Machine Learning for custom model training
C) Azure Cognitive Services - Language service
D) Microsoft Copilot for Microsoft 365

<details>
<summary>Answer</summary>

**Correct: C**

Azure Cognitive Services Language service provides pre-built APIs specifically for text analysis tasks including sentiment analysis, key phrase extraction, language detection, and named entity recognition. This is a pre-built solution optimized for these specific NLP tasks.

**Why the others are wrong:**
- Azure OpenAI Service provides access to advanced language models but requires more complex prompt engineering and is typically used for generative AI tasks, conversational AI, or more complex scenarios - overkill and more expensive for basic sentiment analysis and key phrase extraction
- Azure Machine Learning is for building and training custom models from scratch, which requires data science expertise and significant development time - unnecessary when pre-built APIs are available
- Microsoft Copilot for Microsoft 365 is an AI assistant integrated into Microsoft 365 applications for end-user productivity, not an API service for integrating AI capabilities into custom applications

</details>

---

**Q7.** A company wants to use Microsoft Defender for Cloud to improve their security posture. The security team needs to understand which Azure resources have vulnerabilities and receive recommendations to fix them. Which Defender for Cloud capability addresses this need?

A) Cloud Workload Protection Platform (CWPP) with threat detection alerts
B) Conditional Access policies for identity protection
C) Azure Policy compliance dashboard
D) Cloud Security Posture Management (CSPM) with secure score and recommendations

<details>
<summary>Answer</summary>

**Correct: D**

Cloud Security Posture Management (CSPM) in Defender for Cloud continuously assesses resources, identifies misconfigurations and vulnerabilities, provides a secure score, and offers prioritized recommendations to improve security posture. This directly addresses the need to identify vulnerabilities and get remediation guidance.

**Why the others are wrong:**
- CWPP (Cloud Workload Protection) provides threat detection and response for active attacks and suspicious activities, not vulnerability assessment and configuration recommendations
- Conditional Access policies control authentication and access based on conditions but don't assess resource vulnerabilities or provide security recommendations
- Azure Policy tracks compliance with organizational standards but doesn't provide security vulnerability assessment or prioritized security recommendations like Defender for Cloud's secure score

> ⚠️ Frequently missed on the exam — read the options carefully.

</details>

---

**Q8.** An organization is evaluating Azure AI services and wants to ensure their AI solutions follow responsible AI principles. Which principle specifically addresses ensuring AI systems work reliably and safely under expected conditions?

A) Fairness - AI systems should treat all people fairly
B) Transparency - users should understand how AI systems make decisions
C) Accountability - people should be accountable for AI systems
D) Reliability and Safety - AI systems should perform reliably and safely

<details>
<summary>Answer</summary>

**Correct: D**

Reliability and Safety is the responsible AI principle that ensures AI systems perform consistently, handle errors gracefully, and operate safely under expected and unexpected conditions. This includes rigorous testing and monitoring.

**Why the others are wrong:**
- Fairness addresses avoiding bias and ensuring AI doesn't discriminate or treat different groups unfairly - not about operational reliability
- Transparency focuses on explainability and helping users understand AI decisions and behavior - not about whether systems work reliably
- Accountability ensures there are governance frameworks and human oversight for AI systems - not about the technical reliability of system performance

</details>

---

