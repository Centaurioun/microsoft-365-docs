---
title: Loop experience examples based on admin settings
ms.author: jenz
author: jenzamora
manager: jtremper
audience: Admin
ms.topic: article
ms.service: loop
ms.reviewer: michalbr, dancost
ms.date: 06/03/2025
ms.localizationpriority: medium
search.appverid: MET150
ms.collection: 
- M365-collaboration
- essentials-compliance
- magic-ai-copilot
description: View example screenshots illustrating Loop experiences when admin settings are customized from their default configurations.
f1.keywords:
- CSH
ms.custom: 
- NewAdminCenter_Update
- chat-teams-channels-revamp
appliesto: 
- Microsoft Teams
---

# Loop experience examples based on admin settings

## Default configuration

The following screens depict expected user experience for when the [Loop admin settings](loop-admin-configuration.md) are in the default state of Enabled.

### Loop components in Teams and Outlook

Loop components can be created and sent in Teams and Outlook messages. When the Loop component hyperlink is pasted, the experience is an interactive Loop component in the message.

:::image type="content" source="media/outlook-web-draft.png" alt-text="Screenshot showing an Outlook draft message containing an interactive Loop component":::
Outlook draft message with Loop component

:::image type="content" source="media/teams-web-message.png" alt-text="Screenshot showing a Teams sent message containing an interactive Loop component":::
Teams sent message with same Loop component

### Loop components in the Loop app

:::image type="content" source="media/loop-spv-full.png" alt-text="Screenshot showing the Loop component editor and viewer for a Loop component":::
Loop component editor/viewer enabling full screen interaction with the same Loop component

:::image type="content" source="media/loop-createnew-full.png" alt-text="Screenshot showing the Loop app user interface for creating new components or workspaces":::
Loop app user experience for creating new components or new workspaces

## Expected user experience when Loop creation is disabled

When admin controls are set to Disabled, users cannot create new Loop files or new SharePoint Embedded containers. Existing Loop files and workspaces remain accessible; users can still find, open, and edit them if they have the appropriate permissions. No existing data is deleted.

Loop content and icons may still appear in Microsoft 365 apps, including Microsoft365.com and the Loop component viewer/editor (loop.cloud.microsoft). Previously created files remain visible and accessible, and shared links continue to work as permitted by file permissions.

There are no additional licensing requirements for the Loop component viewer/editor beyond OneDrive access. Users can access Loop content via loop.cloud.microsoft or the All apps view in Microsoft365.com. To hide the Loop icon in the All apps view, disable OneDrive access for those users or use a conditional access policy to block access to loop.cloud.microsoft.

## Loop workspace creation Disabled, Loop component creation Enabled

### Loop components in Teams and Outlook, unchanged

Refer to the above [Loop components in Teams and Outlook](#loop-components-in-teams-and-outlook) as the configuration and experience is the same in this example.

### Loop components in the Loop app, Loop workspace creation Disabled

In this example, the user has never experienced workspace creation in an Enabled state. Therefore, there are no workspaces, no My workspace personal workspace, and no ability to create new workspaces. The Loop component editor/viewer is still accessible in this configuration to enable full screen interaction with any Loop component created in other applications such as Teams, Outlook.

:::image type="content" source="media/loop-spv.png" alt-text="Screenshot showing the Loop component editor and viewer for a Loop component, with workspace creation turned off by the administrator":::
Loop component editor/viewer enabling full screen interaction with a Loop component

If a user access the Loop app directly in this configured state, this is the experience when clicking the Create button. Note that there are no options available because the admin control for workspace creation has been Disabled.

:::image type="content" source="media/loop-app-workspace-create-disabled.png" alt-text="Screenshot showing the Loop app Create menu clicked, with workspace creation turned off by the administrator":::
Loop app Create menu clicked, with workspace creation turned off by the administrator

### Loop workspace experience when workspace creation is Disabled after initial Enablement

In this example, the user was first configured in a workspace creation Enabled state. They created some workspaces. Then, the administrator changed the configuration for them to Disable workspace creation. They are no longer able to create new content, but the content they previously created is still visible and the permissions on each workspace and file control their ability to edit or view.

:::image type="content" source="media/loop-app-workspace-create-disabled-withcontent.png" alt-text="Screenshot showing the Loop app Create menu clicked, with workspace creation turned off by the administrator, and previously created content visible":::
Loop app Create menu clicked, showing previously created content, and workspace creation turned off by the administrator

## Related topics

- [Summary of Compliance, Lifecycle, Governance](loop-compliance-summary.md)
- [Requirements](cpcn-loop-requirements.md)
- [Storage](loop-storage.md)
- [Permissions](cpcn-loop-permission.md)
- [Admin toggles](loop-admin-configuration.md)
- [UX examples for admin toggle states](loop-ux-examples.md)
- [Managing SharePoint Embedded containers](cpcn-loop-spe-management.md)
- [Overview of Loop components in Microsoft 365](loop-components-teams.md)
- [Use Loop components in Outlook](https://support.microsoft.com/office/9b47c279-011d-4042-bd7f-8bbfca0cb136)
- [Use Loop components in OneNote](https://support.microsoft.com/office/use-loop-components-in-onenote-ed8a43d9-f6fd-4ad6-bc9d-8841db4da459)
- [Loop components in Whiteboard](https://support.microsoft.com/office/loop-components-in-whiteboard-c5f08f54-995e-473e-be6e-7f92555da347)
- [Get started with Microsoft Loop - Microsoft Support](https://support.microsoft.com/office/get-started-with-microsoft-loop-9f4d8d4f-dfc6-4518-9ef6-069408c21f0c)
