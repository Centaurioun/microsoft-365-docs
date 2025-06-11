---
title: Usage analytics for the Employee Self-Service agent
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
description: Learn how to access usage analytics for the Employee Self-Service agent.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Usage analytics for the Employee Self-Service agent

You can use different intefaces to monitor ESS agent usage depending on the role in your organization that is in charge of monitoring analytics.

As an application or service owner with the Environment Maker role, you can view analytics in Copilot Studio by navigating to the **Analytics** tab.

For advanced reporting requirements, you can integrate Azure Application Insights with Copilot Studio to gather more telemetry.

## Auditing and logging

The ESS agent is built on Copilot and Power Platform. You can therefore use auditing capabilities from these platforms to log and monitor usage.

### Audit with Microsoft Purview

Microsoft Purview provides features for a comprehensive audit record of end-user activities when interacting with agents. [Learn how to audit user interactions with agents in Microsoft Purview.](/power-platform/release-plan/2024wave2/microsoft-copilot-studio/audit-user-interactions-agents-purview)

[Audit logs for Copilot and AI activities](/purview/audit-copilot).

### Audit with Azure Application Insights

You can [use Azure Application Insights to capture telemetry for custom Copilot Agents.](/microsoft-copilot-studio/advanced-bot-framework-composer-capture-telemetry?tabs=webApp)

### Security information and event management (SIEM)

For any SIEM integrations, use Application Insights or the Power Platform Dataverse auditing capabilities.

[Manage Dataverse auditing](/power-platform/admin/manage-dataverse-auditing)

[Integrate Microsoft Sentinel and Power Platform to better monitor and protect your low-code solutions.](/power-platform/blog/power-apps/integrating-microsoft-sentinel-and-power-platform-to-better-monitor-and-protect-your-low-code-solutions/?msockid=28f06f3913456b75279c7a3712dc6a44)
