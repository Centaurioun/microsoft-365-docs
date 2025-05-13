---  
title: Microsoft 365 Copilot app settings for IT admins
description: The Microsoft 365 Copilot app has features and settings that Enterprise and organization admins can configure. Admins can turn on search, pin Microsoft 365 Copilot Chat, allow or block agents, allow pages and notices, and map the Copilot key to the Microsoft 365 Copilot app.
author: MandiOhlinger
ms.author: mandia
manager: laurawi
ms.date: 05/12/2025
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

- Lists and describes the different settings that affect the Microsoft 365 Copilot app.
- Provides article links that have more information about configuring the feature.

This article applies to:

- Microsoft 365 Copilot

## Prerequisites

To use the features in this article, you need the following role-based access control (RBAC) roles:

- **Global administrator** - This role can deploy the Microsoft 365 Copilot app to users and user groups.
- **Office Apps admin** - This role can create the Cloud policies for the Microsoft 365 Copilot app.

To learn more, see [Admin roles in the Microsoft 365 admin center](/microsoft-365/admin/add-users/about-admin-roles).

## Settings that configure the app experience

When users open the Microsoft 365 Copilot app, there's a navigation bar. You can show or hide some features on the navigation bar, depending on your license.

:::image type="content" source="media/microsoft-365-copilot-app-admin-settings/microsoft-365-copilot-app-left-navigation.png" alt-text="Screen shot that shows the Microsoft 365 Copilot app left navigation and its features for users with a Microsoft 365 Copilot license.":::

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

## Settings that allow or block the Copilot app

There are several settings in the Microsoft 365 admin center that affect the availability of the Copilot app. There is a hierarchy. The settings with a higher hierarchy, like 1 or 2, overwrite settings with a lower hierarchy, like 3 or 4.

The following table lists the settings and their hierarchy.

| Setting | Hierarchy | Related content |
|  --- | --- | --- |
| **No users in the organization can install** | 1 <br/><br/> This settings overrides all other settings. | This **tenant-level** setting prevents all users in your organization tenant from installing the Copilot app (and Copilot Chat). Admins can still install the Copilot app (and Copilot Chat). <br/><br/> [Microsoft 365 admin center](https://admin.microsoft.com) > **Settings** > **Integrated Apps** > **Available apps** > **Copilot** > **Users** tab > **No users in the organization can install** |
| **Deploy app** | 2 <br/><br/> This setting overrides any settings with a 3 or 4 hierarchy. | This **per-user** setting allows all the users you select to access the Copilot app (and Copilot Chat). <br/><br/> [Microsoft 365 admin center](https://admin.microsoft.com) > **Settings** > **Integrated Apps** > **Available apps** > **Copilot** > **Overview** tab > **Deploy app** |
| **Microsoft 365 Copilot license** | 2 <br/><br/> This license overrides any settings with a 3 or 4 hierarchy. | This **per-user** license allows users with the assigned Copilot license to access the Copilot app (and Copilot Chat). <br/><br/> [Microsoft 365 admin center](https://admin.microsoft.com) > **Billing** > **Licenses** > **Microsoft 365 Copilot** |
| **Specific users/group in the organization can install** | 3 <br/><br/> This setting overrides any settings with a 4 hierarchy. | This **per-user** setting allows all the users you select to access the Copilot app (and Copilot Chat). <br/><br/> [Microsoft 365 admin center](https://admin.microsoft.com) > **Settings** > **Integrated Apps** > **Available apps** > **Copilot** > **Users** tab > **Specific users/group in the organization can install** |
| **Block app** | 4 <br/><br/> | This **per-user** setting prevents all the users you select from accessing the Copilot app (and Copilot Chat). <br/><br/> [Microsoft 365 admin center](https://admin.microsoft.com) > **Settings** > **Integrated Apps** > **Available apps** > **Copilot** > **Overview** tab > **Block app** |
| **Pin Microsoft 365 Copilot Chat** | 4 <br/><br/> | This **tenant-level** setting lets you allow or prevent users from pinning the Copilot Chat app to the navigation bar, and is a tenant-level setting. <br/><br/> For example, **Do not pin Copilot Chat to the navigation bar** blocks Copilot Chat for the organization tenant. <br/><br/> [Microsoft 365 admin center](https://admin.microsoft.com) > **Copilot** > **Settings** > **Pin Microsoft 365 Copilot Chat** |

Here's an example:

You use the **Block app** setting to block the Copilot app for a select group of users. Then, you assign some of these same users the **Microsoft 365 Copilot license**.

Users with this Copilot license can use the Microsoft 365 Copilot app. It's allowed because a **Microsoft 365 Copilot license** overrides the **Block app** setting.

---

**PREVIOUS**

- **Block app at the tenant level**

  By default, all users in your organization can use the Microsoft 365 Copilot app. You can block the app using the Microsoft 365 admin center. If you select **No users in the organization can install**, the app is blocked for all users in your organization. This setting overrides all other Copilot settings and is the most restrictive setting.

  1. Sign into the **[Microsoft 365 admin center](https://admin.microsoft.com)** as the Global Administrator. Select **Settings** > **Integrated Apps** > **Available apps** tab, search for Copilot and select the Copilot app:

      :::image type="content" source="media/microsoft-365-copilot-app-admin-settings/microsoft-365-admin-center-add-copilot-app.png" alt-text="Screenshot that shows the Microsoft 365 admin center, integrated apps, and selecting the Copilot app." lightbox="media/microsoft-365-copilot-app-admin-settings/microsoft-365-admin-center-add-copilot-app.png":::

  1. In the **Users** tab, select **No users in the organization can install**.

      - **All users in the organization can install** (default)
      - **Specific users/group in the organization can install**

  To learn more, see [Allow users to install Copilot app](/copilot/manage#manage--chat-on-the-web-in-the-microsoft-365--app-and-in-outlook).

- **Deploy the app to users or user groups**

  1. Sign into the **[Microsoft 365 admin center](https://admin.microsoft.com)** as the Global Administrator.
  1. Select **Settings** > **Integrated Apps** > **Available apps** tab, search for Copilot and select the Copilot app.
  1. In the **Overview** tab, select **Deploy app**.

      :::image type="content" source="media/microsoft-365-copilot-app-admin-settings/microsoft-365-admin-center-deploy-copilot-app.png" alt-text="Screenshot that shows the Microsoft 365 admin center, integrated apps, and deploying the Copilot app.":::

To learn more, see [Get started with Integrated apps](/microsoft-365/admin/manage/test-and-deploy-microsoft-365-apps).

> [!TIP]
> You can also use a mobile device management (MDM) service like [Microsoft Intune](/intune/intune-service/fundamentals/what-is-intune) to deploy apps to devices. To learn more, see [add apps to Intune](/intune/intune-service/apps/apps-add) and [assign apps using Intune](/intune/intune-service/apps/apps-deploy).



## Related articles

- [What is the Microsoft 365 Copilot app?](microsoft-365-copilot-app-overview.md)
- [Updated Windows and Microsoft 365 Copilot Chat experience](/windows/client-management/manage-windows-copilot)
