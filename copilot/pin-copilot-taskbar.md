---
title: Pin Microsoft 365 Copilot to the Windows Taskbar
description: "Learn how to improve the use of Microsoft 365 Copilot across your organization by pinning it to the Windows taskbar."
f1.keywords:
- NOCSH
ms.author: aaroncz
author: aczechowski
manager: dansimp
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

As an admin, you can use a single toggle in the Microsoft 365 admin center to automatically install and pin the Microsoft 365 Copilot app to the Windows taskbar on managed devices. When you enable this setting, Microsoft Intune delivers the Microsoft 365 Copilot app and pins it at the end of the taskbar. Windows 11 devices also respect user behaviors for unpinning the app.

> [!NOTE]
> This information is specific to the Microsoft 365 Copilot app and the Windows taskbar. You can also pin the Copilot Chat experience to the navigation bar in Microsoft 365 apps. For more information, see [Pin Microsoft 365 Copilot Chat to the navigation bar](pin-copilot-chat-navbar.md).

## Before you begin

To configure Copilot taskbar pinning in the Microsoft 365 admin center, you need to be assigned one of the following roles:

- Intune Administrator
- AI Administrator

## Configure settings

To access this setting:

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/).
1. Go to **Copilot** > **Settings** > **User Access**.
1. Select the setting to **Pin M365 Copilot app to Windows taskbar**.

> [!NOTE]
> Only commercial Windows 11 devices running the latest supported build and enrolled in Microsoft Intune receive the app installation and taskbar pinning.

## Pinning options

When you configure this setting, you can choose one of the following options:

- **Pin M365 Copilot to the taskbar (recommended)**:

  The Microsoft 365 Copilot app is automatically pinned to the Windows taskbar. It uses a StartLayout.xml policy via Intune. The user isn't notified of this action.

  The user can manually unpin the app from the taskbar. On Windows 11 devices, the user's preference is respected during future policy refreshes.

- **Do not pin M365 Copilot**:

  The M365 app pinned in Windows taskbar.

You can change these settings at any time. Changes take up to 48 hours to apply on devices and might require a restart.

## More resources

- [Pin Microsoft 365 Copilot Chat to the navigation bar](pin-copilot-chat-navbar.md)
- [Configure the Windows Taskbar Pinned Apps with Policy Settings](/windows/configuration/taskbar/pinned-apps?tabs=intune&pivots=windows-11)
- [Create a policy using settings catalog in Microsoft Intune](/intune/intune-service/configuration/settings-catalog)
