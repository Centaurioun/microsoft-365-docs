---  
title: Microsoft 365 Copilot reports that help admins monitor usage.
description: Learn about the different Microsoft 365 Copilot reporting options available for admins. Get an overview of the Copilot readiness and usage reports in the Microsoft 365 admin center, Copilot Dashboard, Power BI templates, and Microsoft Purview audit logs.
author: MandiOhlinger
ms.author: mandia
manager: laurawi
ms.date: 03/27/2025
ms.topic: overview
ms.service: microsoft-365-copilot
ms.subservice: 
ms.localizationpriority: medium
ms.collection: 
- scotvorg
- m365copilot
- magic-ai-copilot
ms.custom:  
ms.reviewer: alejanl, camillepack
search.appverid: MET150
f1.keywords: Copilot reporting options, Copilot usage reports, Microsoft 365 Copilot reports, Power BI templates, Purview audit logs
audience: Admin
ai-usage: ai-assisted
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Microsoft 365 Copilot reporting options for admins

There are several reporting options that can help admins monitor [Microsoft 365 Copilot](microsoft-365-copilot-overview.md) usage and performance. These reports provide insights into how Copilot is used within the organization, which allows admins to make informed decisions about its deployment and usage.

These reports include:

- Microsoft 365 Copilot readiness and usage reports in the Microsoft 365 admin center
- Copilot Dashboard in Viva Insights
- Advanced Insights Analyst and Power BI templates in Viva Insights
- Power Platform Admin Center (PPAC) - ??
- Microsoft Purview audit Logs

This article provides an overview of the different reporting options available for Microsoft 365 Copilot admins.

This article applies to:

- Microsoft 365 Copilot

## Before you begin

To use the reporting features described in this article, you need to sign into different portals with the appropriate permissions:

- **[Microsoft 365 admin center](https://admin.microsoft.com)**: You need to be a **Microsoft 365 Global Administrator** to configure some of the features. To use the features, users must be members of the **AI administrator** role.
- **Copilot Dashboard**: You need to be a **Microsoft 365 Global Administrator** to enable the Copilot Dashboard and delegate access to **Viva Insights**.
- **Advanced Insights Analyst and Power BI templates in Viva Insights**: You need to be a **Microsoft 365 Global Administrator** to configure the features. To use the features, users must be members of the **Insights Analyst** role.
- **Power Platform Admin Center (PPAC)**: You need to be a Power Platform admin or have the appropriate permissions to access the Power Platform Admin Center. ??
- **[Microsoft Purview portal](https://purview.microsoft.com)**: You need to search the audit logs, which is included in the **Audit Manager** role.

## Copilot readiness and usage reports in the Microsoft 365 admin center

The Microsoft 365 admin center provides Copilot readiness and usage reports:

- **[Readiness report](/microsoft-365/admin/activity-reports/microsoft-365-copilot-readiness)** - This report shows how ready your organization is to adopt Microsoft 365 Copilot. It helps you identify the users that are eligible for Copilot, assign licenses, and monitor the Microsoft 365 apps usage that Copilot integrates with.

- **[Usage report](/microsoft-365/admin/activity-reports/microsoft-365-copilot-usage)** - This report shows how Microsoft 365 Copilot is used in your organization. It gives admins insight into Copilot adoption, user activity, and agent usage. It can help you to understand how users are interacting with Copilot, including in Microsoft 365 apps.

### Open the reports

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) as the **Microsoft 365 Global Administrator**.
1. Assign the **AI Administrator** role to the users who need to access these reports.
1. The AI Admins can start using the reports:

    1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) as the **AI Administrator**.
    1. Select **Reports** > **Usage**.

        :::image type="content" source="media/microsoft-365-copilot-reports-for-admins/microsoft-365-admin-center-reports.png" alt-text="In Microsoft 365 admin center, select reports and then select usage.":::

    1. Select **Microsoft 365 Copilot** > **Readiness** or **Usage**:

        :::image type="content" source="media/microsoft-365-copilot-reports-for-admins/microsoft-365-admin-center-usage.png" alt-text="In Microsoft 365 admin center reports, select Microsoft 365 Copilot and then readiness or usage." lightbox="media/microsoft-365-copilot-reports-for-admins/microsoft-365-admin-center-usage.png":::

To learn more about these reports, see:

- [Microsoft 365 Copilot readiness report](/microsoft-365/admin/activity-reports/microsoft-365-copilot-readiness)
- [Microsoft 365 Copilot usage report](/microsoft-365/admin/activity-reports/microsoft-365-copilot-usage)

## Copilot Dashboard in Viva Insights

The Copilot Dashboard offers a comprehensive view of Copilot's usage metrics and provides actionable insights. It includes data from different sources, and provides a centralized location for monitoring Copilot. For example, you can get metrics, usage statistics, and measure the impact of Copilot.

1. Sign into the [Microsoft 365 admin center](https://admin.microsoft.com/) as the **Microsoft 365 Global Administrator**.
1. [Enable the Copilot Dashboard](/viva/insights/advanced/admin/manage-settings-copilot-dashboard) and [delegate access](/viva/insights/org-team-insights/delegate-access) to the users who need it.
1. The users can start using the Copilot Dashboard:

    1. In Teams, in the left navigation, select the ellipses, and search for **Viva Insights**.
    1. In **Viva Insights**, select **Copilot Dashboard**.

To learn more, see:

- [Manage settings for the Microsoft Copilot Dashboard](/viva/insights/advanced/admin/manage-settings-copilot-dashboard)
- [Delegate access to organizational insights and Copilot Dashboard](/viva/insights/org-team-insights/delegate-access)
- [Microsoft Copilot Dashboard for Microsoft 365 customers](/viva/insights/org-team-insights/copilot-dashboard)

## Advanced Insights Analyst and Power BI templates in Viva Insights

The Analysis page in Microsoft Viva Insights includes Power BI templates and metrics designed for Copilot. These templates allow analysts to create custom reports and visualizations to better understand Copilot's impact and usage.

1. Sign into the [Microsoft 365 admin center](https://admin.microsoft.com/) as the **Microsoft 365 Global Administrator**.
1. [Set up Viva Insights](/viva/insights/advanced/setup-maint/setup-overview) and assign the **Insights Analyst** role to the analysts who need access to Viva Insights.

    For the complete steps, see [Viva Insights setup checklist](/viva/insights/advanced/setup-maint/setup-overview).

1. Make sure the **Insights Analyst** users have the [Power BI Desktop app installed](https://www.microsoft.com/download/details.aspx?id=58494) on their devices.
1. The **Insights Analyst** users can [set up Copilot queries in Viva Insights](/viva/insights/advanced/analyst/copilot-query).

To learn more, see:

- [Advanced insights introduction](/viva/insights/advanced/introduction-to-advanced-insights)
- [Power BI report templates](/viva/insights/advanced/analyst/templates/introduction-to-templates)
- [Set up your queries using Microsoft 365 Copilot in Viva Insights](/viva/insights/advanced/analyst/copilot-query)

## Power Platform Admin Center (PPAC) - ??

The Power Platform Admin Center (PPAC) includes tools and reports for monitoring Copilot within the Power Platform environment. These reports help admins manage and optimize Copilot's performance and usage.

- **Requirements:** Access to the Power Platform Admin Center (PPAC).
- **Features:** Performance reports, usage monitoring, optimization tools.

To learn more, see [Power Platform admin center](/power-platform/admin/new-admin-center).

## Microsoft Purview audit Logs

The Microsoft Purview audit logs provide detailed logs of Copilot activities, compliance tracking, and security auditing. This data helps admins track and audit all actions taken by Copilot within the organization. These logs also help admins maintain compliance and security ??How??.

1. Sign in to the [Microsoft Purview portal](https://purview.microsoft.com) with a role that can search audit logs, like **Audit Manager**.

    For a list of roles and what they can do, see [Roles and role groups in Microsoft Defender for Office 365 and Microsoft Purview](/defender-office-365/scc-permissions).

1. Select **Solutions** > **Audit**.

    :::image type="content" source="media/microsoft-365-copilot-reports-for-admins/microsoft-purview-portal-solutions-audit.png" alt-text="In the Microsoft Purview portal, select solutions and then select audit.":::

1. In **Search** > **Workloads**, select **AIApp** and **Copilot**. Select **Search**. This step searches the audit log search results to only show activities related to Microsoft 365 Copilot. You can also get granular and set a date range and more.

   :::image type="content" source="media/microsoft-365-copilot-reports-for-admins/microsoft-purview-portal-audit-search.png" alt-text="In the Microsoft Purview portal audit feature, go to workloads and select some search options."lightbox="media/microsoft-365-copilot-reports-for-admins/microsoft-purview-portal-audit-search.png":::

To learn more, see:

- [Get started with auditing solutions](/purview/audit-get-started)
- [Microsoft Purview audit logs for Copilot and AI activities](/purview/audit-copilot).

## Related articles

- [Microsoft 365 Copilot Setup](microsoft-365-copilot-setup.md)
- [Activity Reports in Microsoft 365](/microsoft-365/admin/activity-reports/activity-reports)
- [Power Platform Admin Center Analytics](/power-platform/admin/analytics-powerapps) - ??
