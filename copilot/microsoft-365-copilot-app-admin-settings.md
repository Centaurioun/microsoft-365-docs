---  
title: Microsoft 365 Copilot app settings for IT admins
description: The Microsoft 365 Copilot app has features and settings that Enterprise and organization admins can configure. Admins can turn on search, pin Microsoft 365 Copilot Chat, allow or block agents, allow pages and notices, and map the Copilot key to the Microsoft 365 Copilot app.
author: MandiOhlinger
ms.author: mandia
manager: laurawi
ms.date: 05/07/2025
ms.topic: overview
ms.service: microsoft-365-copilot
ms.subservice: 
ms.localizationpriority: medium
ms.collection: 
- scotvorg
- m365copilot
- magic-ai-copilot
ms.custom:  
ms.reviewer: libbymc
search.appverid: MET150
f1.keywords: 
audience: Admin
ai-usage: ai-assisted
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Microsoft 365 Copilot app features that admins can control

The [Microsoft 365 Copilot app](microsoft-365-copilot-app-overview.md) is an everyday AI productivity app for work or school.

The app includes some settings and features that IT admins can configure, including pinning Microsoft 365 Copilot Chat, allowing or blocking agents, and more.

This article:

- Shows you how to make the Copilot app available to users in your organization.
- Lists and describes the different settings that affect the Microsoft 365 Copilot app.
- Provides article links that have more information about configuring the feature.

This article applies to:

- Microsoft 365 Copilot

## Prerequisites

To use the features in this article, you need the following role-based access control (RBAC) roles:

- **AI administrator** - This role can deploy the Microsoft 365 Copilot app to users and user groups.
- **Office Apps admin** - This role can create the Cloud policies for the Microsoft 365 Copilot app.

To learn more, see [Admin roles in the Microsoft 365 admin center](/microsoft-365/admin/add-users/about-admin-roles).

> [!TIP]
> Microsoft recommends you sign in with the least privileged role that you need to complete your task. Typically, the Global Administrator role is too powerful for most tasks, including managing the features described in this article.

## Step 1 - Make the app available to users

By default, all users in your organization can:

- Download and install the Microsoft 365 Copilot app.
- Go to [M365Copilot.com](https://M365Copilot.com) and get the app experience.

Admins can manage the Copilot app installation on user devices. There are two ways to make the app available to users:

- **Option 1: Let users install the app themselves**

  By default, all users in your organization can install the Microsoft 365 Copilot app. You can use the Microsoft 365 admin center to change this setting.

  1. Sign into the **[Microsoft 365 admin center](https://admin.microsoft.com)** as the AI Administrator.
  1. Select **Settings** > **Integrated Apps** > **Available apps** tab, search for Copilot and select the Copilot app (??Is this the Copilot app, or the Copilot Chat app? What is the M365 Copilot app??):

      :::image type="content" source="media/microsoft-365-copilot-app-admin-settings/microsoft-365-admin-center-add-copilot-app.png" alt-text="Screenshot that shows the Microsoft 365 admin center, integrated apps, and selecting the Copilot app." lightbox="media/microsoft-365-copilot-app-admin-settings/microsoft-365-admin-center-add-copilot-app.png":::

  1. In the **User** tab, select one of the following options:

      - **All users in the organization can install** (default)
      - **Specific users/group in the organization can install**

  To learn more, see [Allow users to install Copilot app](/copilot/manage#manage--chat-on-the-web-in-the-microsoft-365--app-and-in-outlook).

- **Option 2: Deploy the app to users or user groups**

  1. Sign into the **[Microsoft 365 admin center](https://admin.microsoft.com)** as the AI Administrator.
  1. Select **Settings** > **Integrated Apps** > **Available apps** tab, search for Copilot and select the Copilot app (??Is this the Copilot app, or the Copilot Chat app? What is the M365 Copilot app??).
  1. In the **Overview** tab, select **Deploy app** ??Need a screenshot with it not grayed out??.

      :::image type="content" source="media/microsoft-365-copilot-app-admin-settings/microsoft-365-admin-center-deploy-copilot-app.png" alt-text="Screenshot that shows the Microsoft 365 admin center, integrated apps, and deploying the Copilot app.":::

To learn more, see [Get started with Integrated apps](/microsoft-365/admin/manage/test-and-deploy-microsoft-365-apps).

> [!TIP]
> You can also use a mobile device management (MDM) service like [Microsoft Intune](/intune/intune-service/fundamentals/what-is-intune) to deploy apps to devices. To learn more, see [add apps to Intune](/intune/intune-service/apps/apps-add) and [assign apps using Intune](/intune/intune-service/apps/apps-deploy).

## Step 2 - Configure the app experience

When users open the Microsoft 365 Copilot app, there's a navigation bar. You can show or hide some features on the navigation bar, depending on your license.

:::image type="content" source="media/microsoft-365-copilot-app-admin-settings/microsoft-365-copilot-app-left-navigation.png" alt-text="Screen shot that shows the Microsoft 365 Copilot app left navigation and its features.":::

The following table lists the Copilot app settings that you can configure.

| Setting | Description | Related content |
|---|---|---|
| Search | ✅ Turned on by default <br/><br/>In the **[Microsoft 365 admin center](https://admin.microsoft.com)** > **Settings** > **Search & intelligence**, you can turn on Microsoft Search in the Copilot app. By default, Microsoft Search is allowed and turned on.<br/><br/> You can also enable **Item insights** and show recommended files. Users can turn off Item insights, but we recommend that it stays on. | - [Set up Microsoft Search](/microsoftsearch/setup-microsoft-search) <br/> - [Item insights in Microsoft 365](/graph/item-insights-overview) |
| Chat | ✅ Pinned by default, depending on license. <br/><br/> Depending on your license, Microsoft 365 Copilot Chat might be automatically pinned in the Copilot app. If not, you can pin Chat to the Copilot app. | [Pin Microsoft 365 Copilot Chat to the navigation bar](pin-copilot.md). <br/><br/> There are Chat features you can configure that affect the Chat experience in the Copilot app, like allowing web searches. To learn more, see [Manage Microsoft 365 Copilot Chat](/copilot/manage).|
| Agents | ✅ Built-in agents turned on by default <br/><br/>In the **[Microsoft 365 admin center](https://admin.microsoft.com)** > **Settings** > **Integrated Apps**, admins can deploy or block agents from showing in the Copilot app. End users can also add agents to their Copilot app experience. | [Manage agents for Microsoft 365 Copilot](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps) |
| Pages | ✅ Allowed by default <br/><br/>Use Cloud Policy to allow users to:<br/><br/> - Create and view Copilot Pages in the Copilot app <br/> - Create and view Loop workspaces and files in the Copilot app | [Loop admin policies for Copilot Pages, Copilot Notebooks, Loop components, and Loop workspaces](/microsoft-365/loop/loop-components-configuration) |
| Notebooks | ✅ Allowed by default <br/><br/>Use Cloud Policy to allow users to create and view Copilot Notebooks in the Copilot app. | [Loop admin policies for Copilot Pages, Copilot Notebooks, Loop components, and Loop workspaces](/microsoft-365/loop/loop-components-configuration) |
| Create | ✅ Allowed by default <br/><br/>Pending https://office.visualstudio.com/MAX/_workitems/edit/10046002. ?? | |
| Copilot Key and Windows + C shortcut | ✅ Configured by default <br/><br/>Admins can map the Copilot key to the Microsoft 365 Copilot app. End users can also manually configure. | [Policy CSPs to manage the Copilot key](/windows/client-management/manage-windows-copilot#policies-to-manage-the-copilot-key) <br/><br/>You can also use the [Microsoft Intune settings catalog](/intune/intune-service/configuration/settings-catalog) (Windows AI category) to configure the hardware key on the keyboard. |

## Related articles

- [What is the Microsoft 365 Copilot app?](microsoft-365-copilot-app-overview.md)
- [Updated Windows and Microsoft 365 Copilot Chat experience](/windows/client-management/manage-windows-copilot)
