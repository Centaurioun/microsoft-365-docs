---
title: Use the Microsoft 365 admin center to manage your Shifts connection to Blue Yonder Workforce Management
author: lana-chin
ms.author: jtremper
manager: jtremper
ms.reviewer: harrywong
ms.topic: how-to
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Learn how to manage your Shifts connection to Blue Yonder Workforce Management in the Microsoft 365 admin center.
ms.localizationpriority: high
ms.collection:
  - M365-collaboration
  - m365-frontline
  - teams-1p-app-admin
appliesto:
  - Microsoft Teams
  - Microsoft 365 for frontline workers
ms.date: 12/20/2024
---

# Use the Microsoft 365 admin center to manage your Shifts connection to Blue Yonder Workforce Management

## Overview

The [Microsoft Teams Shifts connector for Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)  enables you to integrate the Shifts app in Microsoft Teams with Blue Yonder Workforce Management (Blue Yonder WFM). Your frontline workers can seamlessly view and manage their schedules in Blue Yonder WFM from within Shifts.

You can use the [Shifts connector wizard](shifts-connector-wizard.md) in the Microsoft 365 admin center or [PowerShell](shifts-connector-blue-yonder-powershell-setup.md) to create a connection and connection instances. After they're set up, you can manage them in the Microsoft 365 admin center.

The Connector Management Console page lists each connection and connection instance that you've set up, along with information such as health status and sync interval details. You can also access the wizard to create a new connection and connection instances or make changes to any of your existing ones. Select the name of a connection instance to view the details of any errors.

> [!NOTE]
> You can also use PowerShell to manage a connection. For example, you can view an error report, change connection settings, and disable sync. To learn more, see [Use PowerShell to manage your Shifts connection to Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

## Manage

1. In the left navigation of the [Microsoft 365 admin center](https://admin.microsoft.com/), choose **Setup**, and then under **Featured collections**, select **Frontline workers**.
2. Select **Connector Management Console**.

    Here, you'll see a list of all the connections and connection instances if you've already set them up through the wizard or PowerShell, along with information about each one.

    :::image type="content" source="media/shifts-connector-blue-yonder-manage.png" alt-text="Screenshot of the Connector Management page in the Microsoft 365 admin center, showing a list of connections." lightbox="media/shifts-connector-blue-yonder-manage.png":::

### Manage your connection

- To create a new connection, select **Add connection** at the top of the page.
- To update connection settings, choose **Edit** next to an existing connection. You'll see the Connection settings pane, where you can update the settings that you want.

### Manage your connection instances

> [!IMPORTANT]
> Before you map a Blue Yonder WFM instance to a team in Teams, check whether the team has schedule entities such as shifts or time off. If the team has an existing schedule with schedule entities, [remove the schedule entities from the team](shifts-connector-wizard.md#remove-schedule-entities-from-teams-you-want-to-map) before you map a Blue Yonder WFM instance to it. If you don't remove schedule entities before mapping, you'll see duplicate shifts.

- To create a new connection instance, select **Create instance**. You're taken to the wizard, where you can [choose your settings and create mappings](shifts-connector-wizard.md#create-a-connection-instance).
- To change an existing connection instance, under **Actions**, select **Edit**. You're taken to the wizard, where you can [update the settings and mappings](shifts-connector-wizard.md#create-a-connection-instance).
- To delete an existing connection instance, under **Actions**, select **Delete**. You can't undo this action.
- To view more details about an existing connection instance, select its name. On the details page, you'll see health information, including ongoing errors (if any), and mappings. You can also choose **Edit** to update settings in the wizard or **Back** to return to the Connector Management Console page.

  :::image type="content" source="media/shifts-connector-blue-yonder-manage-details.png" alt-text="Screenshot of the details page for a connection, showing connector health and mappings information." lightbox="media/shifts-connector-blue-yonder-manage-details.png":::

For a complete list of error messages and how to resolve them, see [List of error messages](#list-of-error-messages) later in this article.

#### Edit connection instance

To edit your connection instance settings, choose the data that your Shifts users can see and change. You have the following options for these settings:

- **Shifts users will not see provider data**: Data won't sync between Blue Yonder WFM and Shifts.
- **Shifts users can see provider data**: Data syncing is unidirectional from Blue Yonder WFM to Shifts.
- **Shifts users can see and change provider data**: Data syncing is bidirectional between Blue Yonder WFM and Shifts.

> [!IMPORTANT]
> Before you disable a feature by selecting the **Shifts users will not see provider data** option, be aware that:
>
> - If the **Schedules, groups, shifts, and activities** setting is disabled, then all other settings, such as **Time off** and **Employee availability**, and more, are also disabled.
> - If the **Open shift** setting is disabled, **Open shift request** is also disabled.
> - If the **Time off** setting is disabled, **Time off request** is also disabled.

> [!IMPORTANT]
> If you chose any of the following options to disable open shifts, open shift requests, swap requests, or time off requests, there's another step you need to do to hide the capability in Shifts.
>
> - Open shifts: **Shifts users will not see provider data**
> - Swap requests: **Shifts users will not see provider data**
> - Time off requests: **Shifts users will not see provider data**
>
> After you edit your settings, make sure you follow the steps to [disable open shifts, open shifts requests, swap requests, and time off requests](shifts-connector-wizard.md#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests).

To edit your connection instance mappings, you can:

- Add new mappings, by following the same process as when you first create your connection instance. See [Map Blue Yonder WFM instances to teams](shifts-connector-wizard.md#map-wfm-instances-to-teams)
- Edit existing mappings to update the team in Teams to which a Blue Yonder WFM instance is connected.
  If you're mapping to team in Teams that previously used Shifts, make sure you [remove schedule entities from teams you want to map](shifts-connector-wizard.md#remove-schedule-entities-from-teams-you-want-to-map).
- Delete active mappings, either by clearing the checkbox of the mapped Blue Yonder WFM instance, or by uploading the CSV file with the mapping rows removed.
  
## List of error messages

Here's the list of error messages that you may encounter and information to help you resolve them.

|Error type |Error details |Resolution |
|---------|---------|---------|
|Unable to authenticate workforce management system.|The workforce management system account credentials you've provided are invalid or this account doesn't have the required permissions.|Update your WFM service account credentials in the connection settings page. To do this, go to your Microsoft 365 admin center and choose **Edit** next to the connection on the Connector Management Console page.|
|Unable to authenticate Graph. |Authentication failed. Ensure that you've entered valid credentials for the designated actor and have the required permissions.|Make sure that your Microsoft 365 system account (also known as designated actor) is added as a team owner. Or, update your Microsoft 365 system account to the correct team owner. To do this, in the Microsoft 365 admin center, choose **Edit** next to the connection instance on the Connector Management Console page. You're redirected to the wizard and, on the Sync Settings page, you can update the Microsoft 365 system account.|
|Some users have failed to map correctly|Mapping failed for some users: \<X\> succeeded, \<X\> failed Microsoft Entra users and \<X\> failed workforce management system users.|Use the [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult) cmdlet or [this PowerShell script](shifts-connector-powershell-manage.md#user-mapping-errors) to identify the users for whom the mapping failed. Make sure that the users in the mapped team match the users in the WFM instance.|
|Unable to map a team or teams in this batch |This designated actor profile doesn't have team ownership privileges. |Make sure that your Microsoft 365 system account (also known as designated actor) is added as a team owner. Or, update your Microsoft 365 system account to the correct team owner. To do this, in the Microsoft 365 admin center, choose **Edit** next to the connection instance on the Connector Management Console page. You're redirected to the wizard and, on the Sync Settings page, you can update the Microsoft 365 system account. |
|&nbsp; |This team is already mapped to an existing connection instance. |Unmap the team from the existing connection instance by using the [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) cmdlet. Or, create a new connection to remap the team.|
|&nbsp; |This timezone is invalid. The timezone passed in isn't using tz database format.|Make sure that the time zone is correct, and then remap the team.|
|&nbsp; |We can't find this connection instance.|Map the team to an existing connection instance.|
|&nbsp; |This Microsoft Entra team couldn't be found.|Make sure that the team exists or create a new team.|

## Related articles

- [Shifts connectors](shifts-connectors.md)
- [Use the Shifts connector to connect Shifts to Blue Yonder Workforce Management](shifts-connector-wizard.md)
- [Use PowerShell to connect Shifts to Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md)
- [Use PowerShell to manage your Shifts connection to Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Manage the Shifts app](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
