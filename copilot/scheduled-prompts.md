---
title: "Manage Scheduled prompts for Microsoft 365 Copilot"
f1.keywords:
- NOCSH
ms.author: camillepack
author: camillepack
manager: scotv
ms.date: 05/15/2025
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- scotvorg
- m365copilot
- magic-ai-copilot
description: "Learn about managing Scheduled prompts for Microsoft 365 Copilot, admin controls, data policies, and user management steps."
---

# Manage scheduled prompts for Microsoft 365 Copilot

Scheduled prompts in Microsoft 365 Copilot allow users to automate Copilot prompts to run at set times and frequencies in Microsoft Teams, Office.com/chat, and Microsoft Outlook for the web and Desktop. As an admin, you can manage this feature for your organization.

## Before you begin

You must have both of the following licenses to manage scheduled prompts:

- Microsoft 365 Copilot license (in the Copilot subscription)

Before you start using the scheduled prompts feature, ensure that optional connected experiences are enabled for your users. Optional connected experiences are enabled by default, but one way you can check is by reviewing the "Allow the use of additional optional connected experiences in Office" policy setting in [Cloud Policy service for Microsoft 365](/microsoft-365-apps/admin-center/overview-cloud-policy).

Additionally, if you block all new connectors by default using Power Platform Data Loss Prevention (DLP) policies, you need to run the following command to explicitly reclassify the connector:

```powershell
$connectorsToReclassify = @([pscustomobject]@{
 id = "/providers/Microsoft.PowerApps/apis/shared_bizchat"
 name = "Copilot for Microsoft 365"
 type = "providers/Microsoft.PowerApps/apis"
})
Add-ConnectorsToPolicy -PolicyName {TENANT_DLP_POLICY_GUID} -Connectors $connectorsToReclassify -Classification {'Confidential'|'General'}
```

To learn more about adding connectors to policies, see [Add-ConnectorsToPolicy](/powershell/module/microsoft.powerapps.administration.powershell/add-connectorstopolicy).

## Admin controls

To use the scheduled prompts feature as an admin, no action is required if no DLP policies are in place and if optional connected experiences are enabled. However, if you have DLP policies in place that block new connectors, you might need to run the command script mentioned previously. You can check if you have such policies in the [Power Platform admin center](https://admin.powerplatform.microsoft.com).

If you prefer to not have this feature available to your organization, you can use [Cloud Policy](https://config.office.com/officeSettings/officePolicies) to set the "Allow the use of additional optional connected experiences in Office" policy setting to Disabled. For more information, see [Admin controls for optional connected experiences](/microsoft-365-apps/privacy/optional-connected-experiences#admin-controls-for-optional-connected-experiences).

If you disable optional connected experiences, this action prevents anyone in your organization from seeing scheduled prompts in Copilot. Be aware that disabling optional connected experiences turns off other features in Microsoft 365 apps (such as Word, Excel, and PowerPoint) that your users might be using. For a list of those features, see [Overview of optional connected experiences in Office](/microsoft-365-apps/privacy/optional-connected-experiences).

> [!NOTE]
> Your users can individually turn off optional connected experiences by changing their account privacy settings, even if you have enabled optional connected experiences for your users. For more information, see [Your privacy settings](/microsoft-365-apps/privacy/optional-connected-experiences#your-privacy-settings).

Scheduled prompts are supported by the Microsoft 365 environment in Power Platform. This environment is automatically created when a user creates a scheduled prompt for the first time. To learn more about permissions, access, and data policies, see [Power Platform security roles and privileges](/power-platform/admin/security-roles-privileges) 

## Disabling scheduled prompts

:::image type="content" source="media/prompts-org-policy.png" alt-text="Screenshot showing the pop-up that informs users of their organization's data policy." lightbox="media/prompts-org-policy.png":::

If you disable this feature after someone in your organization has already used it:

- Users will no longer be able to manage previously scheduled prompts.
- Sessions for previously run scheduled prompts continue to exist.
- Previously scheduled prompts will continue to execute until their schedule finishes.
- Users will no longer see the Scheduled prompts icon or the prompt management menu if optional connected experiences are disabled.

## Inventory scheduled prompts

For admins with Global Administrator and Power Platform Administrator roles, you can use a PowerShell script to inventory the scheduled prompts created by users in your organization. For instructions on how to do this, see [Copilot Actions admin scripts guide](copilot-admin-actions-scripts.md).

## User controls

:::image type="content" source="media/prompt-set-up.png" alt-text="Screenshot showing the setup text for a new scheduled prompt in Copilot." lightbox="media/prompt-set-up.png":::

Your users can find the scheduled prompts feature by hovering over a prompt they have submitted to Copilot. When a user selects the `Save and activate` button to confirm the scheduled prompt, a user's prompt information is sent to the Power Automate and Power Platform system, and the [Power Automate terms of service and privacy policy](/power-platform/admin/wp-compliance-data-privacy) apply.

To manage their scheduled prompts, users can follow these steps:

1. In the Copilot chat window, select the dropdown menu (**...**), and then **Scheduled prompts**.
2. Select the prompt management pane.
3. From there, users can view and delete their scheduled prompts.

Users signed in with their work/school account can also turn off optional connected experiences, even if their admin has the setting on. For more details, reference [Your privacy settings with optional connected experiences](/microsoft-365-apps/privacy/optional-connected-experiences).

:::image type="content" source="media/scheduled-prompts-save.png" alt-text="Screenshot showing the options to schedule a prompt for Microsoft 365 Copilot.":::

Users can schedule up to 10 prompts to run at specific times, with responses delivered to the Chat pane of their Microsoft 365 Copilot Chat experience. These prompts can be set to run on a recurring basis, ensuring users receive necessary information aligned with their workflow. Responses from scheduled prompts are bolded and have a recurring icon to help users identify them easily.

To learn more about prompts for your users, see [Learn about Copilot prompts](https://support.microsoft.com/topic/learn-about-copilot-prompts-f6c3b467-f07c-4db1-ae54-ffac96184dd5).
