---  
title: Microsoft 365 Copilot reports that help admins monitor usage.
description: Learn about the different Microsoft 365 Copilot reporting options available for admins. Get an overview of the Copilot readiness and usage reports in the Microsoft 365 admin center, Copilot Dashboard, Power BI templates, and Microsoft Purview audit logs.
author: MandiOhlinger
ms.author: mandia
manager: laurawi
ms.date: 04/07/2025
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
- Usage metrics and actionable insights in the Viva Insights Copilot Dashboard
- Advanced Insights Analyst and Power BI templates in Viva Insights
- Copilot agent analytics in the Power Platform admin center
- Detailed audit logs of Copilot activities in the Microsoft Purview portal

This article provides an overview of the different reporting options available for Microsoft 365 Copilot admins.

This article applies to:

- Microsoft 365 Copilot

## Before you begin

To use the reporting features described in this article, you need to sign into different portals with the appropriate permissions:

- **[Microsoft 365 admin center](https://admin.microsoft.com)**: You need to be a **Microsoft 365 Global Administrator** to configure some of the features. To use the features, users must be members of the **AI administrator** role.
- **Copilot Dashboard**: You need to be a **Microsoft 365 Global Administrator** to enable the Copilot Dashboard and delegate access to **Viva Insights**.
- **Advanced Insights Analyst and Power BI templates in Viva Insights**: You need to be a **Microsoft 365 Global Administrator** to configure the features. To use the features, users must be members of the **Insights Analyst** role.
- **[Power Platform admin center](https://admin.powerplatform.microsoft.com) (PPAC)**: You need to be a Power Platform admin or have the appropriate permissions to access the Power Platform Admin Center. ??

  ??Link to PPAC roles

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

1. Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) as the **Microsoft 365 Global Administrator**.
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

## Copilot Studio agent reports in Power Platform admin center

In Copilot Studio, you can [create agents](/microsoft-365-copilot/extensibility/ecosystem) that extend Microsoft 365 Copilot to your data and services. They can be customized to help your organization users with specific and focused tasks.

When you create agents in Copilot Studio, each agent automatically gets analytics data. When users use your agents, sessions are also automatically created. The Power Platform admin center shows this analtyics data, including consumption reports and agent activities.

You can use these reports to get insights into the performance and usage. Use this information to monitor the effectiveness of your agents and make data-driven decisions to optimize their performance.

To learn more, see

- [Key concepts – Analytics in Copilot Studio](/microsoft-copilot-studio/analytics-overview)
- [Set up your development environment for Microsoft 365 Copilot](/microsoft-365-copilot/extensibility/ecosystem)

Based on licensing, there are two approaches to consuming agents - Metered agents (pay as you go and pre-purchased message pack) and non-metered agents (included in the license).

### Analytics for metered agents

This approach is a consumption-based model. You can pay-as-you-go or purchase a message pack with a set number of messages. These options are ideal for organizations that want to control their usage and costs.

To view the analytics for metered agents, use the Power Platform admin center.

1. Sign into the [Power Platform admin center](https://admin.powerplatform.microsoft.com) as the **System Administrator**.
2. Select **Manage** > **Tenant settings**. Add users to the **Copilot Studio authors** role. Users in this group can create agents in Copilot Studio and view the analytics for the agents they created.

    To view all reports of all agents, sign in as ??

    To learn more, see [Assign a security role to a user](/power-platform/admin/assign-security-roles).

3. The **Copilot Studio authors** go to **Licensing** > **Copilot Studio** > **Summary**, and see the following reports:

    - Message capacity
    - Sessions capacity

### Analytics for each agent

This approach is a license-based model. You can use the agents included in your license without any additional costs. This option is ideal for organizations that want to use Copilot Studio agents without worrying about usage limits or costs.

To assign Copilot Studio licenses, use the Microsoft 365 admin center. To view the analytics for non-metered agents, use Copilot Studio.

1. Sign into the [Microsoft 365 admin center](https://admin.microsoft.com/) as the **License admin**. Assign Copilot Studio licenses to the users who need to create agents.

    To learn more, see:

    - [About admin roles in the Microsoft 365 admin center](../../admin/add-users/about-admin-roles.md)
    - [Assign licenses and manage access to Copilot Studio](/microsoft-copilot-studio/requirements-licensing)

1. The Copilot Studio users sign into [Copilot Studio](https://copilotstudio.microsoft.com).
1. Select **Agents** > select your agent > **Analytics** tab.

    To learn more, see [Review and improve agent effectiveness in Copilot Studio](/microsoft-copilot-studio/analytics-improve-agent-effectiveness).

## Microsoft Purview audit Logs

The Microsoft Purview audit logs provide detailed logs of Copilot activities, compliance tracking, and security auditing. This data helps admins track and audit all actions taken by Copilot within the organization.

With these logs, admins can access granular reporting, including the promtps entered by users.

1. Sign in to the [Microsoft Purview portal](https://purview.microsoft.com) with a role that can search audit logs, like **Audit Manager**.

    For a list of roles and what they can do, see [Roles and role groups in Microsoft Defender for Office 365 and Microsoft Purview](/defender-office-365/scc-permissions).

1. Select **Solutions** > **Audit**.

    :::image type="content" source="media/microsoft-365-copilot-reports-for-admins/microsoft-purview-portal-solutions-audit.png" alt-text="In the Microsoft Purview portal, select solutions and then select audit.":::

1. In **Search** > **Workloads**, select **AIApp** and **Copilot**. Select **Search**. This step searches the audit log search results to only show activities related to Microsoft 365 Copilot. You can also get granular and set a date range and more.

   :::image type="content" source="media/microsoft-365-copilot-reports-for-admins/microsoft-purview-portal-audit-search.png" alt-text="In the Microsoft Purview portal audit feature, go to workloads and select some search options."lightbox="media/microsoft-365-copilot-reports-for-admins/microsoft-purview-portal-audit-search.png":::

To learn more, see:

- [Get started with auditing solutions](/purview/audit-get-started)
- [Microsoft Purview audit logs for Copilot and AI activities](/purview/audit-copilot).
- [Considerations for DSPM for AI & data security and compliance protections for Copilot](/purview/ai-microsoft-purview-considerations)

## Related articles

- [Microsoft 365 Copilot Setup](microsoft-365-copilot-setup.md)
- [Activity Reports in Microsoft 365](/microsoft-365/admin/activity-reports/activity-reports)

