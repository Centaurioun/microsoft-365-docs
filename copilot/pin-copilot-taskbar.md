---
title: Pin Microsoft 365 Copilot to the Windows Taskbar
description: "Learn how to improve the use of Microsoft 365 Copilot across your organization by pinning it to the Windows taskbar."
f1.keywords:
- NOCSH
ms.author: aaroncz
author: aczechowski
manager: dansimp
ms.reviewer: christin,vmirapur
ms.date: 07/08/2025
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- Tier2
- scotvorg
- M365-subscription-management 
- Adm_O365
- Adm_TOC
- m365copilot
- magic-ai-copilot
---

# Pin Microsoft 365 Copilot to the Windows taskbar

> [!IMPORTANT]
> This information is currently provided as a preview. The feature is expected to be available at the end of July 2025.

As an admin, you can pin the Microsoft 365 Copilot app to the Windows taskbar of managed devices. This behavior gives users quick access to the Copilot app, which includes Chat, Search, Agents (if enabled), Notebooks, and Create. If your organization has an active Intune license, use the Microsoft 365 admin center to automatically pin the app on all Windows 10 and Windows 11 Intune-managed devices with the app installed. This single toggle simplifies the pinning process instead of manually creating and deploying a StartLayout policy.

> [!NOTE]
> This information is specific to the Microsoft 365 Copilot app and the Windows taskbar. You can also pin the Copilot Chat experience to the navigation bar in Microsoft 365 apps. For more information, see [Pin Microsoft 365 Copilot Chat to the navigation bar](pin-copilot-chat-navbar.md). To understand the difference between the Copilot app and Copilot Chat, see [Decide which Copilot is right for you](which-copilot-for-your-organization.md).

## Prerequisites

- To configure Copilot taskbar pinning in the Microsoft 365 admin center, you need to be assigned the **Intune Administrator** role.

- To configure this setting in the Microsoft 365 admin center, your organization must have an active Intune license.

  > [!TIP]
  > If you don't have an Intune license, you can pin the app by directly using the StartLayout configuration. For more information, see [Configure the Windows Taskbar Pinned Apps with Policy Settings](/windows/configuration/taskbar/pinned-apps?tabs=intune&pivots=windows-11).

- Install the Microsoft 365 Copilot app before you configure this policy. For more information, see the [Microsoft 365 Copilot adoption guide and overview for IT admins](microsoft-365-copilot-enablement-resources.md).

- To allow users to keep their preference to unpin the app, their device must be running Windows 11 with at least the [servicing update for May 2025 (KB5058499)](https://support.microsoft.com/help/5058499). For more information, see [Windows 11 - release information](/windows/release-health/windows11-release-information).

## Configure settings

:::image type="content" source="media/pin-copilot-taskbar/pin-copilot-taskbar-admin-center-1200.png" alt-text="A screenshot of the Microsoft 365 admin center showing the Copilot setting to Pin Microsoft 365 Copilot app to Windows taskbar." lightbox="media/pin-copilot-taskbar/pin-copilot-taskbar-admin-center-1920.png":::

To configure this setting:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).
1. Go to **Copilot** > **Settings** > **User access**.
1. Select the setting to **Pin Microsoft 365 Copilot app to the Windows taskbar**.

    > [!NOTE]
    > If you already configured an Intune policy for StartLayout, you can't configure this setting in the Microsoft 365 admin center. For more information on how to add the Microsoft 365 Copilot app to your existing policy, see [Deploy the taskbar configuration](/windows/configuration/taskbar/pinned-apps?tabs=intune&pivots=windows-11#deploy-the-taskbar-configuration).
    >
    > If you don't have an active Intune license, this setting isn't available.

1. Choose one of the following options and then select **Save**:

    - **Pin the Microsoft 365 Copilot app to the Windows taskbar for all eligible devices (recommended)**

        Select this option to automatically pin the Microsoft 365 Copilot app to the Windows taskbar. The user isn't notified when this action is applied on the device.

        :::image type="content" source="media/pin-copilot-taskbar/pin-copilot-taskbar.png" alt-text="The Windows taskbar with the Microsoft 365 Copilot app pinned to the far right.":::

        If the user previously pinned the app to their taskbar, this policy doesn't change their configuration.

        The user can manually unpin the app from the taskbar. On Windows 11 devices with at least the [servicing update for May 2025 (KB5058499)](https://support.microsoft.com/help/5058499), the user's preference is respected during future policy refreshes.

    - **Do not pin Copilot app to the Windows taskbar**

        This option is the default setting. When you select this option, managed policy doesn't affect the user's taskbar. In other words, the Microsoft 365 Copilot app isn't pinned to the Windows taskbar unless you take action. Users can still pin the app themselves.

You can change these settings at any time. Changes take up to 48 hours to apply on devices and might require a restart.

## More resources

- [Pin Microsoft 365 Copilot Chat to the navigation bar](pin-copilot-chat-navbar.md)
- [Configure the Windows Taskbar Pinned Apps with Policy Settings](/windows/configuration/taskbar/pinned-apps?tabs=intune&pivots=windows-11)
- [Create a policy using settings catalog in Microsoft Intune](/intune/intune-service/configuration/settings-catalog)
