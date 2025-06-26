---
title: Prerequisites to deploy the Employee Self-Service agent
f1.keywords: NOCSH
ms.author: daisyfeller
author: daisyfell
manager: triciagill
ms.date: 6/20/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.custom: ess-agent
ms.localizationpriority: medium
ms.collection: m365copilot
description: Learn about the prerequisites you need to meet before deploying the Employee Self-Service agent.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Prerequisites to deploy the Employee Self-Service agent

>[!NOTE]
>The Employee Self-Service agent is currently in public preview. Deployment processes are subject to change before this product becomes generally available.

You'll need to confirm the following prerequisites have been met before deploying the Employee Self-Service agent (ESS) to your organization.

## Licensing

The ESS Agent is built on top of Microsoft 365 Copilot. Users will therefore need the following licenses depending on the tools they use at work.

|Role   |Workload/tools   |Licensing and access|
|----------|-----------|------------|
|Users  |Microsoft 365 Copilot    |[Microsoft 365 Copilot](../microsoft-365-copilot-licensing.md)       |
|Users |Microsoft Power Platform*  |[Licensing overview for Power Platform](/power-platform/admin/pricing-billing-skus) </br>[Request limits and allocations](/power-platform/admin/api-request-limits-allocations)|
|Users |Microsoft Teams |[Manage user access to Microsoft Teams](/microsoftteams/user-access) |
|Environment admins and makers |Copilot Studio |[Copilot Studio licensing and subscriptions](/microsoft-copilot-studio/requirements-licensing-subscriptions) |

*Premium licenses are required for some third-party connectors.

## Set up Copilot Studio capacity

The ESS agent uses agent flows. You therefore need to set up the Copilot Studio capacity. [Learn about Copilot Studio capacity](/microsoft-copilot-studio/requirements-messages-management).

### Capacity planning

The ESS Agent operates on Copilot, requiring Copilot licenses. Users without assigned licenses will be automatically billed on a "Pay-as-you-go" basis.  Please refer to  

If ESS Agent is going to be consumed by users without Copilot licenses, then it requires proactive capacity planning ensuring that the consumption cost is optimized for the usage. 

The following are few sample benchmarks to get an idea of capacity plan for ESS Agent deployment: 

## Required roles

The ESS Agent includes several different technical components and configuration areas, which require different Microsoft 365 roles for deployment. It's recommended to use the least privileged role possible to perform each necessary activity. For roles with elevated privileges, use just-in-time access.

|Role |Description |Activities performed |Configuration areas|
|-----|------------|---------------------|-------------------|
|Global admin |User who has permissions to configure and delegate other roles |Assign user roles |Microsoft admin center |
|Power Platform administrator |User who has power to configure Power Platform environments and assign roles within Power Platform |- Create environments </br> - Assign user roles </br> - Install ESS agent |- Power Platform </br> - Microsoft Copilot Studio |
|Power Platform maker |User who has permission to make changes in a specific Power Platform environment. It’s recommended to have the service owner for this agent perform this role. |Configure ESS agent |- Power Platform </br> - Microsoft Copilot Studio |
|ISV administrators |Users who manage third-party solutions |Provide configuration inputs for ISV applications |ISV application's administration and configuration interface |
|Information security |Infrastructure team who manage and control enterprise application security policies |- Allowlist inbound requests for ISV endpoints </br> - Manage single sign-on configurations |- Network firewall policies </br> - Signle sign-on applications |
|Change control board |Team that manages changes in an organization relating to deploying an enterprise application |- Approve technical architecture </br> - Approve data security, compliance, and governance policies </br> - Approve responsible AI polices |N/A |

[Learn more about role-based security roles for Power Platform](/power-platform/admin/database-security)

### Non-configuration required roles

These roles don't need to work in the technical configuration areas, but they're crucial to the success of the agent.

- Human resources representatives
- Information technology representatives
- Legal and privacy representatives

All of these roles are responsible for:

- Identifying knowledge sources relating to their area of specialty
- Providing frequent queries
- Identifying sensitive topics
