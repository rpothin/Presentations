# [Power Platform Community Conference](https://powerplatformconf.com/)

- **Date:** October 28-30, 2025
- **Location:** Las Vegas

## [Enhancing Power Platform Governance Through Terraform: Embracing Infrastructure as Code](https://powerplatformconf.com/#!/session/Enhancing%20Power%20Platform%20Governance%20Through%20Terraform:%20Embracing%20Infrastructure%20as%20Code/7663)

### 📝 Abstract
As Power Platform adoption scales, traditional "ClickOps" governance can no longer keep up. This session explores the transformative journey from manual administration to an Infrastructure as Code (IaC) approach, delivering improved efficiency, consistency, and control. We'll discover techniques that reduce manual configuration errors and cut configuration times from days to hours, while outlining strategies for teams to adopt Terraform seamlessly. Through a few practical examples, we will see how DLP policies and environments can be managed using the Power Platform Terraform provider and what it could mean for configuring Power Platform workloads integrated with Azure or Fabric. Attendees will walk away with a blueprint for IaC adoption and ready-to-use Terraform configurations for common governance scenarios.

### 🎨 Presentation Materials
- **📑 Slide Deck:** [Enhancing Power Platform Governance Through Terraform - Embracing Infrastructure as Code](./EnhancingPowerPlatformGovernanceThroughTerraform/Enhancing%20Power%20Platform%20Governance%20Through%20Terraform%20-%20Embracing%20Infrastructure%20as%20Code.pdf)
- **💻 Demo Resources:** [rpothin/ppcc25-terraform-power-platform-governance](https://github.com/rpothin/ppcc25-terraform-power-platform-governance)
- **📹 Demonstrations Recording:** [Enhancing Power Platform Governance Through Terraform: Embracing Infrastructure as Code](https://youtu.be/E8ZBybdeWYQ?si=uYpJaZIivKxQPeAY)

### 🛠️ Resources & References
- [Power Platform Provider | Terraform Registry](https://registry.terraform.io/providers/microsoft/power-platform/latest/docs)
- [microsoft/terraform-provider-power-platform](https://github.com/microsoft/terraform-provider-power-platform)
- [Power Platform Terraform provider | Microsoft Docs](https://learn.microsoft.com/en-us/business-applications/playbook/enterprise-solutions/power-platform-terraform-provider/)
- [Infrastructure as code for Power Platform, a light at the end of the tunnel?](https://medium.com/rapha%C3%ABl-pothin/infrastructure-as-code-for-power-platform-a-light-at-the-end-of-the-tunnel-27674c3d1a25)
- [The Power Platform Infrastructure as Code journey — First stop: Inventory](https://medium.com/rapha%C3%ABl-pothin/the-power-platform-infrastructure-as-code-journey-first-stop-inventory-8c7e789b3d5f)
- [The Power Platform Infrastructure as Code journey — Dawn of transformation](https://medium.com/rapha%C3%ABl-pothin/the-power-platform-infrastructure-as-code-journey-dawn-of-transformation-5b3afc89c505)
- [The Power Platform Infrastructure as Code journey — A bright future](https://medium.com/rapha%C3%ABl-pothin/the-power-platform-infrastructure-as-code-journey-a-bright-future-19d294b8a675)

## [Deep-Dive into Power Platform Managed Security](https://powerplatformconf.com/#!/session/Deep-Dive%20into%20Power%20Platform%20Managed%20Security/7649)

> [!IMPORTANT]
> Presented in collaboration with [Tomas Prokop](https://github.com/TomProkop).

### 📝 Abstract
Keeping track of sensitive data storage locations and diagnosing issues without proper tracing is challenging. Low-code platforms like Power Platform enable users to automate data flows easily, increasing the risk of losing control over sensitive data and facilitating data exfiltration.

Power Platform addresses these challenges through standardized monitoring and security features, making activities within applications more transparent compared to traditional black-box systems.

In this session, we will review native Power Platform logs and explore methods for analyzing telemetry data. The discussion will cover both operational monitoring, such as health metrics and troubleshooting, as well as security-focused topics including log collection, alerting, and incident response. We will demonstrate native integrations of Power Platform with Azure Application Insights (usage monitoring), Microsoft Purview (log collection and compliance management) and Microsoft Sentinel (threat detection and incident response).

### 🎨 Presentation Materials
- **📑 Slide Deck:** [Deep-Dive into Power Platform Managed Security](./DeepDiveIntoPowerPlatformManagedSecurity/Deep-Dive%20into%20Power%20Platform%20Managed%20Security.pdf)
- **💻 Demo Resources:**
   - [Dataverse - Audit logging disabled - Enhanced analytic rule](./DeepDiveIntoPowerPlatformManagedSecurity/Dataverse%20-%20Audit%20logging%20disabled%20-%20Enhanced.yaml) 
   - [KQL queries](./DeepDiveIntoPowerPlatformManagedSecurity/queries.kql)
- **📹 Demonstrations Recording:** [Deep-Dive into Power Platform Managed Security](https://youtu.be/KbKxKhuSOF4?si=Qh_2cu-Y_TiDwZ3u)

### 🛠️ Resources & References
- [Power Platform Managed Security | Microsoft Docs](https://learn.microsoft.com/en-us/power-platform/admin/security/managed-security)
- [Power Platform’s protection — Microsoft Purview Compliance](https://medium.com/rapha%C3%ABl-pothin/power-platforms-protection-microsoft-purview-compliance-d8d5b5ecc2d4)
- [Connect to and manage Microsoft Dataverse in Microsoft Purview | Microsoft Docs](https://learn.microsoft.com/en-us/purview/register-scan-dataverse?tabs=MI)
- [Power Platform’s Protection — Microsoft Purview the data guardian](https://medium.com/rapha%C3%ABl-pothin/power-platforms-protection-microsoft-purview-the-data-guardian-d7bc34620655)
- [Microsoft Sentinel solution for Microsoft Business Apps | Microsoft Docs](https://learn.microsoft.com/en-us/azure/sentinel/business-applications/solution-overview)
- [Code of the resources in the Microsoft Sentinel solution for Microsoft Business Apps | GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Solutions/Microsoft%20Business%20Applications)
- [Power Platform’s Protection — Microsoft Sentinel, the watchtower](https://medium.com/rapha%C3%ABl-pothin/power-platforms-protection-microsoft-sentinel-the-watchtower-dbbccc2516c5)
- [Power Platform Integration with Application Insights | Microsoft Docs](https://learn.microsoft.com/en-us/power-platform/admin/overview-integration-application-insights)