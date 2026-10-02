# Azure Identity, Security, and AI Services - Exam Cheat Sheet

## Microsoft Entra ID (formerly Azure AD) - Identity & Access

### Authentication Methods
| Method | Use Case | Exam Key |
|--------|----------|----------|
| **SSO** | One login, multiple apps | Reduces password fatigue, works across Azure/M365/SaaS |
| **MFA** | Additional verification factor | Something you know + have + are |
| **Passwordless** | FIDO2, Hello, Authenticator | Most secure - eliminates password attacks |

### External Identities
- **B2B**: Partner organizations collaborate with your employees
- **B2C**: Customers sign in with social IDs (Google, Facebook, Microsoft)
- **Exam trap**: B2B ≠ B2C. B2B for business partners, B2C for consumers.

### Conditional Access
**Evaluates**: User, location, device, app, risk level  
**Actions**: Allow, require MFA, block  
**Exam scenario**: Require MFA from untrusted locations, allow normal access from corporate network

## Access Control vs Compliance vs Protection

| Concept | Purpose | Exam Focus |
|---------|---------|------------|
| **RBAC** | WHO can do WHAT (permissions) | Owner/Contributor/Reader roles, custom roles |
| **Azure Policy** | WHAT configs allowed (compliance) | Enforce standards, deny non-compliant resources |
| **Resource Locks** | PREVENT deletion/modification | CanNotDelete, ReadOnly - protection from accidents |

**Exam trap**: Policy enforces compliance, RBAC controls permissions, Locks prevent changes. Different purposes.

## Security Models

### Zero Trust (3 Principles)
1. **Verify explicitly**: Always authenticate/authorize based on all data points
2. **Least privilege access**: Grant minimum necessary permissions
3. **Assume breach**: Minimize blast radius, verify end-to-end encryption

**Exam key**: Zero Trust = never trust, always verify (even inside network)

### Defense-in-Depth (Layers)
Physical → Identity → Perimeter → Network → Compute → Application → Data  
**Exam key**: Multiple security layers - if one fails, others protect

## Microsoft Defender for Cloud

| Component | Function | Exam Scenario |
|-----------|----------|---------------|
| **CSPM** | Security posture, secure score, recommendations | Find misconfigurations and vulnerabilities |
| **CWPP** | Threat detection, security alerts | Detect and respond to active attacks |

**Exam trap**: CSPM for prevention/assessment, CWPP for detection/response

## Azure AI Services (2026 Update)

### Service Selection Guide
| Service | Use Case | Exam Key |
|---------|----------|----------|
| **Azure OpenAI** | GPT-4, generative AI, complex reasoning, content generation | Advanced language models, conversational AI |
| **Cognitive Services - Language** | Sentiment analysis, key phrase extraction, entity recognition | Pre-built NLP APIs, specific text analysis tasks |
| **Cognitive Services - Vision** | Image analysis, OCR, face detection | Pre-built computer vision APIs |
| **Azure Machine Learning** | Custom models, specific use cases | Requires data science skills, build from scratch |

**Exam trap**: Use Cognitive Services for pre-built AI, Azure ML for custom models, OpenAI for generative AI

### Microsoft Copilot Family
- **Microsoft 365 Copilot**: Word, Excel, PowerPoint, Teams productivity
- **GitHub Copilot**: Code completion, AI pair programming
- **Copilot in Azure**: Azure Portal infrastructure management assistance

**Exam key**: Copilots are AI assistants embedded in Microsoft products (added Jan 2026)

## Responsible AI Principles (FRPITA)

1. **Fairness**: Treat all people fairly, avoid bias
2. **Reliability and Safety**: Perform reliably under expected conditions
3. **Privacy and Security**: Protect data, respect privacy
4. **Inclusiveness**: Empower everyone, consider diverse needs
5. **Transparency**: Users understand how AI makes decisions
6. **Accountability**: People accountable for AI systems

**Exam trap**: Reliability = consistent performance; Fairness = no bias; Transparency = explainability

## Quick Decision Tree

**Need to control WHO can do WHAT?** → RBAC  
**Need to enforce WHAT configs are allowed?** → Azure Policy  
**Need to PREVENT accidental deletion?** → Resource Locks  
**External partners accessing resources?** → B2B  
**Customers signing in with social IDs?** → B2C  
**Pre-built sentiment analysis?** → Cognitive Services Language  
**Generative AI content creation?** → Azure OpenAI  
**Custom ML model?** → Azure Machine Learning  
**Find security misconfigurations?** → Defender CSPM  
**Detect active threats?** → Defender CWPP
