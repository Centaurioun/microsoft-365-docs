---
title: "Message consumption - Microsoft 365 activity reports in the admin center"
ms.author: camillepack
author: camillepack
manager: scotv
ms.date: 05/06/2025
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- m365copilot
- magic-ai-copilot
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: "Learn about the Message consumption report in the Microsoft 365 admin center and how it helps to manage costs associated with Microsoft 365 Copilot Chat."
---

# Message consumption - Microsoft 365 activity reports in the admin center

The Message consumption report helps you manage metered consumption costs for Microsoft 365 Copilot Chat. This report gives you visibility into billed messages associated with your Microsoft 365 Copilot pay-as-you-go billing policies and includes key metrics such as:

- Total messages consumed
- Cumulative and daily time series
- Messages per user, per agent, and per agent-user pair.  

## How do I get to the message consumption report?  

1. In the admin center, go to **Reports** > **Usage**.
1. Select **Message consumption** from the Microsoft 365 Copilot dropdown.

## Interpret the Message consumption report

After you [set up pay-as-you-go for Microsoft 365 Copilot Chat](/copilot/microsoft-365/pay-as-you-go/setup), either in the Microsoft 365 admin center or Power Platform admin center, and enabled agent usage in your organization, you'll see a new report including metrics for messages consumed.

To help you mitigate overspending, the report includes alerts when users have consumed more than 2,000 billed messages. To learn more, see [Using agents in Microsoft 365 Copilot Chat](/copilot/agents) and the [overview on enabling agents](/microsoft-copilot-studio/requirements-messages-management), which explains how agents are billed.  

You can filter the report by different periods. The Message consumption report can be viewed over the last 7 or 30 days.

:::image type="content" source="../../media/mc-hero-metric.png" alt-text="Screenshot showing the Message consumption report page in the Microsoft 365 admin center." lightbox="../../media/mc-hero-metric.png":::

>[!NOTE]
> During the preview stage, the report displays a maximum of 30 days of message consumption history. In addition, usage information from before May 3, 2025 won't be available in the report.  

### Messages consumed

The **Messages consumed** metric shows the total billed messages from interactions by users in your organization who do not have a Microsoft 365 Copilot license, and are interacting with agents in Copilot Chat that spin the Copilot Studio meter during the selected period.  

The number of messages consumed depends on the design of the agent, how often end-users interact with it, and the features the agent uses. Each interaction with an agent might use multiple message types simultaneously. For example, an agent grounded in a tenant graph could use 12 messages (10 messages for tenant graph-grounding, and two messages for generative answers) to respond to a single complex prompt from a user.

### Alerts

The **Alert** card is visible in the report when one or more users consumed more than 2,000 messages in the past 30 days. This helps admins identify high-usage users and manage costs more effectively.

:::image type="content" source="../../media/mc-alert.png" alt-text="Screenshot showing the alert box that informs admins about high message consumption.":::

>[!NOTE]
> For preview, the Alerts will remain visible in the report for up to seven days and will disappear after if there are no new users who crossed the threshold.  

### View charts

You can see the following cumulative chart in this report as default view.

:::image type="content" source="../../media/mc-cumulative-chart.png" alt-text="Screenshot showing the chart with a green trend line that shows the cumulative default view for message consumption." lightbox="../../media/mc-cumulative-chart.png":::

The definition of messages consumed is the same as provided earlier.  

You can switch between the **Cumulative view** and **Daily view**.

**Cumulative view** shows you the total number of messages consumed over the selected time frame.  

**Daily view** shows you the messages consumed on a daily basis over the selected time frame.  

#### User details

:::image type="content" source="../../media/mc-user-details.png" alt-text="Screenshot showing a table for user details in the Message consumption report." lightbox="../../media/mc-user-details.png":::

#### Agent details

:::image type="content" source="../../media/mc-agent-details.png" alt-text="Screenshot showing a table for agent details in the Message consumption report." lightbox="../../media/mc-agent-details.png":::
