---
ms.date: 06/10/2025
title: "Manage Copilot Pages and Copilot Notebooks in your organization"
ms.reviewer: dancost, tonchan
ms.author: jenz
author: jenzamora
manager: jtremper
recommendations: true
audience: Admin
f1.keywords:
- NOCSH
ms.service: loop
ms.localizationpriority: medium
ms.topic: how-to
ms.collection:
- Strat_SP_admin
- Microsoft 365-collaboration
- Tier3
- essentials-manage
- magic-ai-copilot
search.appverid:
- SPO160
- MET150
description: "Manage Copilot Pages and Copilot Notebooks in your organization"
---

# Admin policies for Copilot Pages and Copilot Notebooks

Copilot Pages and Copilot Notebooks and their integrations are backed by `.loop` files, stored in user-owned SharePoint Embedded containers. Learn more about [storage and lifecycle](/microsoft-365/loop/cpcn-storage), which is quota combined with SharePoint in your tenant. IT admins can manage creation of Copilot Pages and Copilot Notebooks using Cloud Policy.

## Requirements

Copilot Pages and Copilot Notebooks are a core service integrated into SharePoint and Microsoft 365. See [requirements](/microsoft-365/loop/cpcn-loop-requirements) to learn more about configuration requirements, service connections, and license requirements.

### Microsoft 365 Groups for Cloud Policy

If you want to scope the Cloud Policy settings to only some users in your tenant, you can create or use an existing Microsoft 365 group to define which users in your organization this policy will apply to. To create a Microsoft 365 group, see [Create a Microsoft 365 group](/microsoft-365/admin/create-groups/create-groups).

> [!NOTE]
> This section isn't required if you choose to apply the Cloud Policy settings to all the users in your tenant.

You'll be able to use this group for the Cloud Policy setup procedure specified in [Settings management in Cloud Policy](#settings-management-in-cloud-policy).

If you prefer, you can also create other types of groups to use with Cloud Policy. For more information, see [learn more about creating groups in the Microsoft 365 admin center](/microsoft-365/admin/email/create-edit-or-delete-a-security-group) or [learn more about creating dynamic groups in AzureAD](/azure/active-directory/external-identities/use-dynamic-groups).

## Relation to Loop components

Copilot Pages can be shared as a component. This mechanism relies on Loop components to be enabled in your organization for integrations like Teams, Outlook, Whiteboard, OneNote, or the Loop app to function. If Loop components are not enabled in your organization, Copilot Pages will only be interactive within the M365 Copilot app and Chat experiences that support Copilot Pages. See [Loop admin policies](/microsoft-365/loop/loop-admin-configuration) for information on configuring **Create and view Loop files in Microsoft apps that support Loop**.

## User experience expectations when Copilot Pages and Copilot Notebooks are Disabled

When the IT admin control for creation of Copilot Pages and Copilot Notebooks is set to Disabled, the creation of new Copilot Pages and creation of new SharePoint Embedded containers is prevented. The Pages module in the M365 Copilot app will still be visible. The Notebooks module in the M365 Copilot app will be hidden.

Existing user data isn't deleted, and users can still find, see, and access existing Copilot Pages and Copilot Notebooks in the M365 Copilot app, via shared hyperlinks, and in searches. Access to these files is determined by their permissions, so users with edit access can still open and edit them. The files will still be discoverable using Purview and are exportable by admins.

## Settings management in Cloud Policy

Copilot Pages and Copilot Notebooks check the following [Cloud Policy](/deployoffice/admincenter/overview-cloud-policy) setting:

- **Create and view Copilot Pages and Copilot Notebooks**

1. Sign in to https://config.office.com/ with your Microsoft 365 admin credentials.
1. Select **Customization** from the left pane.
1. Select **Policy Management**.
1. Create a new policy configuration or edit an existing one.
1. From the **Choose the scope** dropdown list, choose either **All users** or select the group for which you want to apply the policy. For more information, see [Microsoft 365 Groups for Cloud Policy](#microsoft-365-groups-for-cloud-policy).
1. In **Configure Settings**, choose one of the following settings:
    - For **Create and view Copilot Pages and Copilot Notebooks**
        - **Enabled**: Copilot Pages and Copilot Notebooks creation and integration are available to the users.
        - **Disabled**: Copilot Pages and Copilot Notebooks creation and integration aren't available to the users.
        - **Not configured**: Copilot Pages and Copilot Notebooks creation and integration are available to the users.
          >[!NOTE]
          >If your organization has [disabled the creation of OneDrive](/sharepoint/manage-user-profiles#disable-onedrive-creation-for-some-users), regardless of the setting noted here, these people in your organization won't be able to create Copilot Pages or Copilot Notebooks.
1. Save the policy configuration.
1. Reassign priority for any security group, if required. (If two or more policy configurations are applicable to the same set of users, the one with the higher priority is applied.)

In case you create a new policy configuration or change the configuration for an existing policy, there can be a delay in the change being reflected as described below:

- If there were existing policy configurations prior to the change, then it will take 90 mins for the change to be reflected.
- If there were no policy configurations prior to the change, then it will take 24 hours for the change to be reflected.

> [!NOTE]
> In order to target only a subset of users in your organization as Enabled for one of these Cloud Policies, create a Group A to target these users, set the Cloud Policy to Enabled in this group. Then create a Group B that targets All users, set the Cloud Policy to Disabled in this group. Then, configure Group A with a priority that evaluates *before* Group B. In Cloud Policy, priority 0 evaluates first, followed by priority 1, then 2, and so on. So for example, Group A with priority 0 will Enable your subset of users, and Group B with priority 1 will only evaluate for users not in Group A, and Disable for the remainder of your users.

## Related topics

- [Overview of Loop components in Teams](/microsoftteams/live-components-in-teams)
- [Use Loop components in Outlook](https://support.microsoft.com/office/9b47c279-011d-4042-bd7f-8bbfca0cb136)
- [Use Loop components in OneNote](https://support.microsoft.com/office/use-loop-components-in-onenote-ed8a43d9-f6fd-4ad6-bc9d-8841db4da459)
- [Loop components in Whiteboard](https://support.microsoft.com/office/loop-components-in-whiteboard-c5f08f54-995e-473e-be6e-7f92555da347)
- [Get started with Microsoft Loop - Microsoft Support](https://support.microsoft.com/office/get-started-with-microsoft-loop-9f4d8d4f-dfc6-4518-9ef6-069408c21f0c)
- [Summary of governance, lifecycle and compliance capabilities for Loop](/microsoft-365/loop/loop-compliance-summary)
