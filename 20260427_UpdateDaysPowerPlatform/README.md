# [Update Days Power Platform](https://power.updatedays.cz/)

- **Date:** April 27-28, 2026
- **Location:** Prague

> [!NOTE]
> [Photos from the conference](https://media.itixo.com/share/bqWhdr6aL6jvMpZ5mm8geB9OzGFBkK6lZy3fSRbaIjf0gnlwlFH7JmfkIxEq3BnTejQ?at=6f70aa47-6840-4720-9e00-f89c2a79ba02).

## Mitigating AI risks from injection, exfiltration and unsafe actions

### 📝 Abstract
AI agents introduce entirely new attack vectors that most organizations are not prepared for. This session takes a red-team perspective: rather than walking through configuration checklists, we will simulate realistic attacks against Power Platform and Copilot Studio agents to show how these threats actually unfold. Using a mix of live attack demonstrations and guided visual walkthroughs grounded in the same realistic business ecosystem, we will show how seemingly helpful agents can be steered from "answer questions" into unsafe actions and data leakage. Along the way, we will unpack the concrete mechanics behind direct and indirect prompt injection (UPIA/XPIA), how tool/connector use can turn mistakes into exfiltration paths, and why over-privileged agent identities ("run as user" / "run as author") increase blast radius. We will also briefly step into the code-first world to cover supply chain poisoning patterns such as "hallucinated packages" and unvetted AI-generated code entering your build and deployment workflow. Throughout the session, we will highlight where common baseline controls (for example, tenant-level switches, DLP, and prompt-only guardrails) tend to fall short against agentic threats, and we will close with concrete mitigations and a practical path forward.

### 🎨 Presentation Materials
- **📑 Slide Deck:** [Mitigating AI risks from injection, exfiltration and unsafe actions](./Mitigating%20AI%20risks%20from%20injection,%20exfiltration%20and%20unsafe%20actions.pdf)
- **📹 Audio Deep Dive:** [Mitigating AI risks from injection, exfiltration and unsafe actions](https://youtu.be/lGtXRfyjzlg)

## Finding security threats and limiting their impact

### 📝 Abstract
Most organizations still discover Power Platform security issues after the fact - through user reports or data exposure. In this session, we’ll build a practical blue-team workflow using the Microsoft Sentinel solution for Microsoft Business Apps (Power Platform + Dataverse) and complementary telemetry (like Application Insights). The story thread is a Copilot Studio agent, but we’ll treat it as a real solution: an agent typically comes with satellite Power Automate flows, Dataverse tables, and sometimes apps. You’ll learn how to make these assets observable, hunt across multiple signal sources, turn hunts into durable detections, and automate triage and containment - with the goal of limiting blast radius and feeding findings back into governance guardrails.

### 🎨 Presentation Materials
- **📑 Slide Deck:** [Finding security threats and limiting their impact](./Finding%20security%20threats%20and%20limiting%20their%20impact.pdf)
- **💻 Demo Resources:** [Demonstration GitHub repository](https://github.com/rpothin/udpp26-finding-security-threats)
- **📹 Audio Deep Dive:** [Finding security threats and limiting their impact](https://youtu.be/Y_4srX_ylEw)

## Deploying Power Platform and Azure infrastructure as code

### 📝 Abstract
Terraform enables self-service Power Platform workspace provisioning and management - reliable, repeatable, and auditable. This session demonstrates a complete pattern: developers request workspaces and safely extend platform configurations, with no portal access to production. Attendees leave with a forkable open-source implementation to adapt for their organization - a foundation for building an internal developer platform for Power Platform.

### 🎨 Presentation Materials
- **📑 Slide Deck:** [Deploying Power Platform and Azure infrastructure as code](./Deploying%20Power%20Platform%20and%20Azure%20infrastructure%20as%20code.pdf)
- **💻 Demo Resources:** [Demonstration GitHub repository](https://github.com/rpothin/udpp26-power-platform-devex-with-terraform)
- **📹 Audio Deep Dive:** [Deploying Power Platform and Azure infrastructure as code](https://youtu.be/seFtYALbDIg)

### 📢 Some personal work teased at the end of the session

- First Power Platform AVM aligned Terraform module: [res-tenantsettings](https://registry.terraform.io/modules/rpothin/res-tenantsettings/powerplatform/latest)
- [Pulumi Power Platform](https://github.com/rpothin/pulumi-powerplatform)

## (Bonus) Panel Discussion - New challenges for governance

### 📝 Abstract

An opening panel discussion on the state of Power Platform governance. Governance practitioners share their perspectives on what has improved, what challenges remain unsolved and how AI agents and citizen development are reshaping governance strategies. Setting the stage for the governance track.

### 🎭 Participants

- **Tomaš Prokop** - Solution Architect at NETWORK
- **Rami Moula** - Solution Architect at Capgemini
- **Jukka Niiranen** - Power Platform Advisor at Niiranen Advisory
- **Casey Burke** - Principal Product Manager at Microsoft
- **Raphael Pothin** - Lead Reliability Engineer at Manulife
