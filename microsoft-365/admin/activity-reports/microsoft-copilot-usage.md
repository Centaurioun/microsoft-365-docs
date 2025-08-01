---
title: "Microsoft 365 admin center – Microsoft 365 Copilot Chat usage"
ms.author: camillepack
author: camillepack
manager: scotv
ms.date: 05/07/2025
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- m365copilot
- magic-ai-copilot
description: "Learn about the Microsoft 365 Copilot Chat usage report and gain insights into the Microsoft 365 Copilot Chat activity in your organization."
---

# Microsoft 365 reports in the admin center – Microsoft 365 Copilot Chat usage

The Microsoft 365 Copilot Chat usage dashboard provides insights into active usage of Microsoft 365 Copilot Chat. The report includes total active users, average daily active users, and active users per app. Usage insights can be viewed as totals and trends for the past 7, 30, 90, or 180-day periods. The report also shows the last activity date per user, anonymized by default. To view all reports, check out [Microsoft 365 Reports in the admin center overview](activity-reports.md).

> [!NOTE]
> The report is currently limited to users without a Microsoft 365 Copilot license that interact with Copilot Chat in Teams, Outlook, Copilot.cloud.microsoft, Microsoft 365 Copilot (app), and Microsoft Edge.

## How do I get to the Microsoft 365 Copilot Chat usage report?

1. In the admin center, go to **Reports** > **Usage**.
2. Select **Microsoft 365 Copilot** > **Copilot Chat**.

## Interpret the Microsoft 365 Copilot Chat usage report

You can use this report to see the usage of Microsoft 365 Copilot Chat in your organization. At the top, you can filter by different periods. The Microsoft 365 Copilot Chat report can be viewed over the last 7 days, 30 days, 90 days, or 180 days.

You can view aggregated numbers for Microsoft 365 Copilot Chat active users and average daily active users:

:::image type="content" source="../../media/copilot-chat-usage.png" alt-text="Screenshot showing the number of active users for Microsoft 365 Copilot Chat usage." lightbox="../../media/copilot-chat-usage.png":::

- **Active users** shows the total number of users who sent at least one message to Microsoft 365 Copilot Chat during the selected period.
- **Average daily active users** indicates the average number of people using Microsoft 365 Copilot Chat per day over the selected period.

In **Recommendations**, the recommended action card highlights where admins can update settings to pin Copilot to make it easier for users in the organization to find and use Copilot in apps like Teams and Outlook.

:::image type="content" source="../../media/microsoft-copilot-pin.png" alt-text="Screenshot showing the pop-up message to pin Copilot for all users.":::

You can see the following summary charts in this report as default view:

:::image type="content" source="../../media/copilot-chat-summary.png" alt-text="Screenshot showing the chart to evaluate adoption by app for Microsoft 365 Copilot Chat." lightbox="../../media/copilot-chat-summary.png":::

- **Summary view** shows you the total usage of Microsoft 365 Copilot Chat of the time frame.
- **Trend view** shows you the daily time trend of Microsoft 365 Copilot Chat of the time frame.

You can switch between Summary view and Trend view. When switching to Trend view, you can select one or multiple entry points in the dropdown list to see daily usage or compare among entry points.

:::image type="content" source="../../media/copilot-chat-adoption.png" alt-text="Screenshot showing the chart in Trend view to analyze adoption by app for Microsoft 365 Copilot Chat." lightbox="../../media/copilot-chat-adoption.png":::

The following table shows app details for active Microsoft 365 Copilot Chat users:

| App               | Details                                                                 | More information |
|-------------------|-------------------------------------------------------------------------|------------------|
| **Edge**          | Microsoft 365 Copilot Chat was used from the sidebar in the Microsoft Edge browser.                     | [Copilot - Microsoft Edge](https://www.microsoft.com/edge/features/copilot) |
| **Microsoft 365 Copilot (app)** | Microsoft 365 Copilot Chat was used in the desktop, mobile, or web version of the Microsoft 365 Copilot (app), including the following entry points: Microsoft365.com, Office.com, M365Copilot.com, Microsoft 365 desktop app, Microsoft 365 mobile app, M365.cloud.microsoft | [Overview of Copilot](/copilot/overview) |
| **Teams**     | Microsoft 365 Copilot Chat was used in Teams.                | [Manage Copilot Chat in Teams](/copilot/manage#manage--chat-in-teams) |
| **Outlook**     | Microsoft 365 Copilot Chat was used in Outlook.                | [Manage Copilot Chat on the web, in the Microsoft 365 Copilot app, and in Outlook](/copilot/manage#manage--chat-on-the-web-in-the-microsoft-365--app-and-in-outlook) |
| **Copilot.cloud.microsoft**     | Microsoft 365 Copilot Chat was used in Copilot.cloud.microsoft.                | [Manage Microsoft 365 Copilot Chat](/copilot/manage#how-to-ensure-users-access--chat) |

You can also export the report data into an Excel .csv file by selecting the ellipses and then **Export** in the top-right corner.

You can view a table list to show each active user who accessed Microsoft 365 Copilot Chat over the past 180 days.

:::image type="content" source="../../media/microsoft-copilot-export.png" alt-text="Screenshot showing the table list of data for active users for Microsoft 365 Copilot Chat." lightbox="../../media/microsoft-copilot-export.png":::

You can also export the report data into an Excel .csv file by selecting the **Export** link. This exports the Microsoft 365 Copilot Chat usage data of all users and enables you to do simple sorting, filtering, and searching for further analysis.

## User last activity table

| Item                        | Description                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| **Username**                | The user's principal name.                                                  |
| **Display name**            | The full name of the user.                                                  |
| **Last activity date (UTC)**| The most recent date on which the user sent a message to Microsoft 365 Copilot Chat in Teams, Outlook, Copilot.cloud.microsoft, Microsoft Edge, or the Microsoft 365 Copilot (app). This date remains fixed even if the timeframe of the report is changed. |
| **Last activity date of Teams (UTC)**| The most recent date on which the user sent a message to Microsoft 365 Copilot Chat in Teams. This date remains fixed even if the timeframe of the report is changed. |
| **Last activity date of Outlook (UTC)**| The most recent date on which the user sent a message to Microsoft 365 Copilot Chat in Outlook. This date remains fixed even if the timeframe of the report is changed.  |
| **Last activity date of Copilot.cloud.microsoft (UTC)**| The most recent date on which the user sent a message to Microsoft 365 Copilot Chat in Copilot.cloud.microsoft. This date remains fixed even if the timeframe of the report is changed. |
| **Last activity date of Microsoft 365 Copilot (app) (UTC)**| The most recent date on which the user sent a message to Microsoft 365 Copilot Chat in Microsoft 365 Copilot (app). This date remains fixed even if the timeframe of the report is changed.  |
| **Last activity date of Edge (UTC)**| The most recent date on which the user sent a message to Microsoft 365 Copilot Chat from the sidebar in the Microsoft Edge browser. This date remains fixed even if the timeframe of the report is changed.  |

## User-specific data de-anonymous/anonymous setting

By default, usernames and display names in the Microsoft 365 Copilot Chat report are anonymous. Global administrators can update settings to unconceal or conceal usernames and display names.

1. In the Microsoft 365 admin center, go to the **Settings** > **Org Settings**, and under the **Services** tab, choose **Reports**.
2. Select **Reports**, and update the setting to “Display Concealed user, group, and site names in all reports”.
3. Select **Save**.

## FAQ

### Does this report include only the Copilot Chat usage for users without a Microsoft 365 Copilot license in the organization?

Yes. To view Copilot Chat usage of Microsoft 365 Copilot licensed users in the organization, refer to the [Microsoft 365 Copilot usage report](microsoft-365-copilot-usage.md) in the Microsoft 365 admin center.
