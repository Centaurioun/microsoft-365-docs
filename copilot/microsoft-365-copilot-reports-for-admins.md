---  
title: Microsoft 365 Copilot reports that help admins monitor usage.
description: Learn about the different Microsoft 365 Copilot reporting options available for admins. Get an overview of the Copilot readiness and usage reports in the Microsoft 365 admin center, Copilot Dashboard, Power BI templates, and Microsoft Purview audit logs.
author: MandiOhlinger
ms.author: mandia
manager: laurawi
ms.date: 04/08/2025
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

There are several reporting options that can help admins monitor [Microsoft 365 Copilot](microsoft-365-copilot-overview.md) usage and performance. These reports provide insights into how Copilot is used within the organization. Admins can use this information to make informed decisions about the Copilot deployment and usage.

These Microsoft 365 Copilot reports include:

- Readiness and usage reports in the Microsoft 365 admin center
- Usage metrics and actionable insights in the Viva Insights Copilot Dashboard
- Advanced Insights Analyst and Power BI templates in Viva Insights
- Copilot agent analytics in the Power Platform admin center and Copilot Studio
- Detailed audit logs of Copilot activities in the Microsoft Purview portal

This article provides an overview of the different reporting options available for Microsoft 365 Copilot admins.

This article applies to:

- Microsoft 365 Copilot

## Before you begin

To use the reporting features described in this article, you need to sign into different portals with the appropriate permissions:

- **[Microsoft 365 admin center](https://admin.microsoft.com)**: You need to be a **Microsoft 365 Global Administrator** to:

  - Add users to the **AI administrator** role. AI admins can access the Copilot readiness and usage reports.
  - Enable the **Copilot Dashboard** and delegate access to the Copilot Dashboard and organizational insights.
  - Set up **Viva Insights** and add users to the **Insights Analyst** role.

- **Power Platform admin center** and **Copilot Studio**:

  - In the [Power Platform admin center](https://admin.powerplatform.microsoft.com), you need to be a **System Administrator** and assign the **Copilot Studio authors** role. Copilot Studio authors can access reports for their agents.
  - In the [Microsoft 365 admin center](https://admin.microsoft.com), you need to be a **License admin** and assign Copilot Studio licenses. In [Copilot Studio](https://copilotstudio.microsoft.com), the licensed users can access their agent reports.

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

The Copilot Dashboard offers a comprehensive view of Copilot's usage metrics and provides actionable insights. It includes data from different sources, and provides a centralized location for monitoring Copilot. For example, you can get metrics, usage statistics, and measure the effect of Copilot.

1. Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) as the **Microsoft 365 Global Administrator**.
1. [Enable the Copilot Dashboard](/viva/insights/advanced/admin/manage-settings-copilot-dashboard) and [delegate access](/viva/insights/org-team-insights/delegate-access) to the users who need it.
1. The users can start using the Copilot Dashboard:

    1. In Teams, in the left navigation, select the ellipses (...), and search for **Viva Insights**.
    1. In **Viva Insights**, select **Copilot Dashboard**.

To learn more, see:

- [Manage settings for the Microsoft Copilot Dashboard](/viva/insights/advanced/admin/manage-settings-copilot-dashboard)
- [Delegate access to organizational insights and Copilot Dashboard](/viva/insights/org-team-insights/delegate-access)
- [Connect the Microsoft Copilot Dashboard to Microsoft 365 customers](/viva/insights/org-team-insights/copilot-dashboard)

## Advanced Insights Analyst and Power BI templates in Viva Insights

The Analysis page in Microsoft Viva Insights includes Power BI templates and metrics designed for Copilot. These templates allow analysts to create custom reports and visualizations to better understand Copilot's effect and usage.

1. Sign into the [Microsoft 365 admin center](https://admin.microsoft.com/) as the **Microsoft 365 Global Administrator**.
1. [Set up Viva Insights](/viva/insights/advanced/setup-maint/setup-overview) and assign the **Insights Analyst** role to the analysts who need access to Viva Insights.

    For the complete steps, see [Viva Insights setup checklist](/viva/insights/advanced/setup-maint/setup-overview).

1. Make sure the **Insights Analyst** users have the [Power BI Desktop app installed](https://www.microsoft.com/download/details.aspx?id=58494) on their devices.
1. The **Insights Analyst** users can [set up Copilot queries in Viva Insights](/viva/insights/advanced/analyst/copilot-query).

To learn more, see:

- [Advanced insights introduction](/viva/insights/advanced/introduction-to-advanced-insights)
- [Power BI report templates](/viva/insights/advanced/analyst/templates/introduction-to-templates)
- [Set up your queries using Microsoft 365 Copilot in Viva Insights](/viva/insights/advanced/analyst/copilot-query)

## Copilot agent reports in Power Platform admin center and Copilot Studio

In Copilot Studio, you can [create agents](/microsoft-365-copilot/extensibility/ecosystem) that extend the capabilities of Microsoft 365 Copilot. Agents are AI-powered assistants that can connect to your data and services, and help users with focused tasks.

When you create agents in Copilot Studio, each agent automatically gets analytics data. When users use your agents, sessions are also automatically created.

To learn more, see:

- [Key concepts – Analytics in Copilot Studio](/microsoft-copilot-studio/analytics-overview)
- [Set up your development environment for Microsoft 365 Copilot](/microsoft-365-copilot/extensibility/ecosystem)

The Power Platform admin center and Copilot Studio provide analytics data for your agents.

Based on licensing, there are two approaches to consuming agents:

- **Consumption-based agents** - You can [pay-as-you-go](./pay-as-you-go/overview.md) or purchase a message pack with a set number of messages (??need link to message pack info??). This approach is a consumption-based model, and is ideal for organizations that want a cost effective way to access Copilot services.

- **Licensed agents** - You can use the agents included in your Microsoft 365 Copilot license without any extra costs. This approach is a license-based model, and is ideal for organizations that want to use Copilot agents without worrying about usage limits or costs.

### Analytics reports for consumption-based agents

To view the analytics for consumption-based agents, use the Power Platform admin center.

1. Sign into the [Power Platform admin center](https://admin.powerplatform.microsoft.com) as the **System Administrator**.
2. Select **Manage** > **Tenant settings**. Add users to the **Copilot Studio authors** role. Users with this role can create agents in Copilot Studio and view the analytics for the agents they create.

    To view all reports of all agents, sign in as ??what's the least privileged role??

    To learn more, see [Assign a security role to a user](/power-platform/admin/assign-security-roles).

3. The Copilot Studio authors can start using the reports:

    1. Sign into the [Power Platform admin center](https://admin.powerplatform.microsoft.com) as the **Copilot Studio author**.
    1. Select **Licensing** > **Copilot Studio** > **Summary**

        ??screenshot??

    1. View the reports:

        - Message capacity
        - Sessions capacity

### Analytics reports for licensed agents

To assign Copilot Studio licenses, use the Microsoft 365 admin center. To view the analytics for the agents, use Copilot Studio.

1. Sign into the [Microsoft 365 admin center](https://admin.microsoft.com/) as the **License admin**. Assign Copilot Studio licenses to the users who need to create agents.

    To learn more, see:

    - [About admin roles in the Microsoft 365 admin center](../microsoft-365/admin/add-users/about-admin-roles.md)
    - [Assign licenses and manage access to Copilot Studio](/microsoft-copilot-studio/requirements-licensing)

1. The Copilot Studio users can start using the reports:

    1. Sign into [Copilot Studio](https://copilotstudio.microsoft.com) as a license Copilot Studio user.
    1. Select **Agents** > select your agent > **Analytics** tab.

        To learn more, see [Review and improve agent effectiveness in Copilot Studio](/microsoft-copilot-studio/analytics-improve-agent-effectiveness).

## Microsoft Purview audit Logs

The Microsoft Purview audit logs provide detailed logs of Copilot activities, compliance tracking, and security auditing. This data helps admins track and audit all actions taken by Copilot within the organization.

With these logs, admins can access granular reporting, including the prompts entered by users.

1. Sign in to the [Microsoft Purview portal](https://purview.microsoft.com) with a role that can search audit logs, like **Audit Manager**.

    For a list of roles and what they can do, see [Roles and role groups in Microsoft Defender for Office 365 and Microsoft Purview](/defender-office-365/scc-permissions).

1. Select **Solutions** > **Audit**.

    :::image type="content" source="media/microsoft-365-copilot-reports-for-admins/microsoft-purview-portal-solutions-audit.png" alt-text="In the Microsoft Purview portal, select solutions and then select audit.":::

1. In **Search** > **Workloads**, select **AIApp** and **Copilot**. Select **Search**. This step searches the audit log search results to only show activities related to Microsoft 365 Copilot. You can also get granular and set a date range and more.

   :::image type="content" source="media/microsoft-365-copilot-reports-for-admins/microsoft-purview-portal-audit-search.png" alt-text="In the Microsoft Purview portal audit feature, go to workloads and select some search options."lightbox="media/microsoft-365-copilot-reports-for-admins/microsoft-purview-portal-audit-search.png":::

To learn more, see:

- [Microsoft Purview auditing solutions](/purview/audit-get-started)
- [Microsoft Purview audit logs for Copilot and AI activities](/purview/audit-copilot).
- [Considerations for Data Security Posture Management (DSPM) for AI & data security and compliance protections for Copilot](/purview/ai-microsoft-purview-considerations)

## Related articles

- [Microsoft 365 Copilot license plans](microsoft-365-copilot-licensing.md)
- [Microsoft 365 Copilot setup](microsoft-365-copilot-setup.md)
- [Activity Reports in Microsoft 365](/microsoft-365/admin/activity-reports/activity-reports)
