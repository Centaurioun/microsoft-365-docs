---
title: "Manage agents for Microsoft 365 Copilot in the Microsoft 365 admin center"
f1.keywords:
- NOCSH
ms.author: camillepack
author: camillepack
manager: scotv
ms.date: 05/29/2025
audience: Admin
ms.topic: concept-article
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: "Learn how to manage agents for Microsoft 365 Copilot in the Microsoft 365 admin center."
---

# Manage agents for Microsoft 365 Copilot in the Microsoft 365 admin center

> [!IMPORTANT]
>
> - This article is intended for IT administrators.
> - The capability is enabled by default in all Microsoft 365 Copilot licensed tenants.
> - The management of agents is currently transitioning to the Copilot Control System. During this transition phase, certain features will still be managed on the Integrated Apps page.

Microsoft 365 Copilot is a new experience in Microsoft 365 that combines the power of large language models with your data and apps in Microsoft 365 to capture natural language commands to produce content and analyze data. It enables access to and use of third-party apps, such as Jira, [Dynamics 365](/microsoft-365-copilot/extensibility/overview-business-applications), or Bing Web Search.

You can manage agents for Copilot using the Copilot Control System in the Microsoft 365 admin center. You can enable, disable, assign, block, or remove agents for your organization, and manage Copilot capabilities and data privacy.

## Overview

Agents enhance the functionality of Copilot by adding search capabilities, custom actions, connectors, and APIs. Agents are custom versions of Microsoft 365 Copilot that combine instructions, knowledge, and skills to perform specific tasks or scenarios. To learn more, see [Get started with agents for Microsoft 365 Copilot](https://support.microsoft.com/topic/get-started-with-agents-for-microsoft-365-copilot-169469d7-328d-4d37-9090-bfc2058a39bd).

Microsoft Copilot Studio is a low-code development platform that offers a graphical environment to build agents tailored to the internal needs of an organization. Copilot Studio enables developers and makers to create and test their applications in a user-friendly interface.

However, before these agents can become available to users, the agents must undergo a streamlined process of submission and approval. To learn more, see [Publish agents](#publish-agents).

The hub Copilot experience shows the list of agents that are available and deployed for the user. Users can toggle it on or off to restrict access of Copilot to any specific agents during the interaction. Users can also add or remove agents in their Copilot experience by right-clicking on the agents and selecting the appropriate option. Users can only access the agents that are allowed by the admin and that they have installed or been assigned to.

## Manage agents in the Microsoft 365 admin center

The following administrator roles can manage agents in the Microsoft 365 admin center:

- AI Admin
- Global Admin
- Global Reader (view-only, no edit)

You can manage agents in the Microsoft 365 admin center by using the **Agents & connectors** page under the [Copilot Control System](/copilot/microsoft-365/microsoft-365-copilot-page). This page allows you to view the list of available, deployed, or blocked apps for your organization. You can:

- Make an agent available to specific users or groups.
- Block or unblock agents for the complete organization.
- Deploy or remove agents for the complete organization or specific users or groups.

As the management of agents transitions to the Copilot Control System, which will become the central hub for all Copilot extensibility management, certain features will still be managed on the Integrated Apps page.

You can view agents from the list of available, deployed, or blocked apps by going to **Copilot** > **Agents & connectors**, or by using the filter option of **Host products** > **Copilot** on the Integrated apps page.

You can also check if a specific app has Copilot support by selecting it from apps list and checking if the app overview mentions **Copilot** as a host product.

### Shared agents

You can also manage shared agents, which are agents that are configured to be used by multiple users or groups within the organization. To learn more, see [Manage shared agents for Microsoft 365 Copilot](manage-shared-agents.md).

## Settings

The following settings are available to manage agents for Copilot:

- Enable or disable agents
- Advanced agent settings

More settings will be added in the future.

### Enable or disable Copilot extensibility

You can enable or disable Copilot extensibility for your organization by using a setting to control who can access agents in your organization.

To do this, follow these steps:

1. Go to **Integrated apps** in the Microsoft 365 admin center.
1. Select **Available apps**, and then the settings icon.
1. Find **Allow the following users access to Copilot agents** and choose your preferred setting.

The setting has three options:

- **All Users** This is the default option and it means that all users in the organization can access agents, subject to the existing app policies and user assignments.
- **No Users** This option means that no users in the organization can access agents, and the third-party agents are disabled in the agents flyout. This option also hides agents from the list of Available and Deployed apps on the Integrated apps page.
- **Specific Users** This option lets you select specific users or groups in your organization to have access to agents. So while all or specific users in your organization may have permissions to install and use apps from the Available apps and Deployed apps lists, only the users or groups you select in this setting can use agents.

> [!NOTE]
> Once extensibility is disabled, the Microsoft pinned Visual Creator agent and entry point for Agent Builder will no longer be visible in BizChat.  Once extensibility is disabled in the tenant, it can take up to 24 hours for agents to disappear for users and for Agent Builder and Visual Creator to disappear.

### Manage how users can install agents

You can assign or unassign agents to specific users or groups by using the same gestures and controls that work for any other app in the Microsoft 365 admin center. You can select an app that has a plugin for Copilot from the Available apps or Deployed apps list and select the **Assign** or **Unassign** option. You can also choose to assign or unassign the app to everyone or specific users or groups. Assigning or unassigning an agent affects its availability and functionality in Copilot and in the other host products, such as Outlook, Teams, or Microsoft 365.

> [!IMPORTANT]
> Developers can [update the existing apps](/microsoft-365-copilot/extensibility/) to work with Microsoft 365 Copilot. If the updated app was pre-approved or pre-installed by an admin, then it'll update for the assigned users and starts working with Copilot. If a developer updates a previously blocked app to work with Microsoft 365 Copilot and then the admins make the app available to the users, then such an app also works with Copilot.

## Actions for agents

The following table describes the actions you can take to manage an agent for your organization:

| **Action** | **Description** |
|------------|-----------------|
| **Publish** | Make an agent available to specific users or groups. This means the agent is listed in the store and can be installed by those users. |
| **Deploy** | Install an agent on behalf of a user by accepting Microsoft Entra permissions for them. This action makes the agent active and usable for specific users or groups. |
| **Remove** | Remove the agent from the inventory. This action is applicable only for first-party or third-party agents. The agent can be re-added to the inventory by acquiring it from the store. |
| **Block** | Prevent any users in the tenant from accessing the agent. This action ensures that the agent cannot be used by anyone in the organization. |

### Publish agents

The publishing process in the Microsoft 365 admin center for agents submitted via Copilot Studio is designed to ensure governance and quality of the custom applications. It also reduces manual work by automating the submission of manifests, freeing developers and admins from tedious tasks. The simplified approval process reduces the time it takes for you to approve apps, making it easier for you to manage custom applications in the Microsoft 365 admin center.

The publishing process involves the following steps:

1. Developers create and test agents in Copilot Studio, which provides a user-friendly interface for inputting the parameters and data for the applications.
1. Developers submit their agents for approval from within Copilot Studio to the Microsoft 365 admin center.
1. You can discover the apps with agents that are submitted but not yet approved in admin center under the **Requested Apps** tab in the Integrated Apps section. The tab shows the name, host products, status, and Copilot readiness of the applications. The status of a new app is `Publish pending` and of an update to an existing app is `Update pending`.
1. You can select a pending application to see more details and metadata, such as the description, requester, request date, and the status. These details help you to make an informed decision on whether to publish or reject the application.
1. You can approve or disapprove any pending application by selecting **Publish** or **Reject**.

   1. If the application is approved, it becomes available to the org users based on the org default settings for custom apps. The application also becomes part of the `Available apps` list in the admin center, where admins can manage user assignments and other settings as any other app.

   1. If the application is disapproved, it is removed from the `Pending approval` list in the admin center, and the status is shared with Copilot Studio. The developer can make changes and resubmit the application for approval.

1. If the developer publishes an update to an existing application, the update is also submitted for approval and follows the same workflow as a new application. The update is shown in the ‘Pending approval’ list with the status `Update pending`. Until the update is approved, the previous version of the application remains available to the users.

### Deploy agents

You can deploy agents across the whole organization or for specific users or groups by using the same gestures and controls that work for any other app in the Microsoft 365 admin center. To do this, follow these steps:

1. In the admin center, go to the Integrated apps page.
1. Select an agent from the list of Available apps.
1. Select **Deploy**.
1. Decide whether to deploy the agents for everyone or specific users or groups.

Deploying an agent affects its availability and functionality in Copilot and in the other host products, such as Outlook, Teams, or Microsoft 365.

### Remove agents

You can remove first-party and third-party agents across the whole organization or for specific users or groups by using the same controls that work for any other app in the Microsoft 365 admin center. To do this, follow these steps:

1. In the admin center, go to the Integrate apps page.
1. Select an agent from the list of Deployed apps.
1. Select **Remove**.
1. Decide whether to remove the agents for everyone or specific users or groups.

Removing an agent affects its availability and functionality in Copilot and in the other host products, such as Outlook, Teams, or Microsoft 365.

### Block or unblock agents

You can block or unblock agents for the complete organization or specific users or groups by using the same controls that work for any other app in the Microsoft 365 admin center. To do this, follow these steps:

1. In the admin center, go to the Integrated apps page.
1. Choose an agent from the list of Available or Deployed apps.
1. Select **Block** or **Unblock**.
1. Decide whether to block or unblock the agent for everyone or for specific users or groups.

Blocking or unblocking an agent affects its availability and functionality in Copilot and other host products, such as Outlook, Teams, or Microsoft 365.

## View and consent to permissions and data access

For detailed information about how Microsoft 365 Copilot uses, protects, and shares organizational information to power extensibility, see [Data, Privacy, and Security for Microsoft 365 Copilot](/microsoft-365-copilot/microsoft-365-copilot-privacy).

## Agent metadata in admin center

You can access key metadata for Copilot agents directly within the publish flow on the Integrated Apps page. This metadata includes details such as the agent’s capabilities, data sources (for example, OneDrive and Sharepoint files and sites, or Graph connectors), and custom actions. It’s important to note that agents are only for declarative agents, meaning they are designed to perform specific tasks based on predefined rules and configurations.
