---
title: "Inventory for Scheduled Prompts"
author: camillepack
ms.author: camillepack
manager: dansimp
ms.service: microsoft-365-copilot
ms.topic: include
description: Learn about using Copilot Actions admin scripts and the prerequisites and steps for various operations.
ms.date: 05/15/2025
---

# Copilot Actions admin scripts guide

Admins can take inventory of scheduled prompts created in their tenant by running PowerShell scripts. The instructions below enable admins to connect to their accounts and view, list, or delete scheduled prompts.

## Prerequisites

To take inventory of scheduled prompts created by users in your organization, you’ll need the following prerequisites:  

- Have the Global Administrator and Power Platform Administrator roles assigned to your user in Azure portal for the tenant on which you want to do operations.
- Use [PowerShell v7.0+](/powershell/scripting/install/installing-powershell).
- Have `Az.Accounts` and `Microsoft.PowerApps.Administration.PowerShell` [modules installed](/powershell/module/powershellget/install-module).
- Have all scripts in the same folder and run the scripts while being in that folder.

To get the System Administrator role on the Copilot scheduled prompts environment, follow these steps:

- Go to [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/environments).
- Find the **Microsoft 365** environment and select it. (This is the default name for Copilot Actions environment; some tenants might use a different name).
- Select **Membership**.
- Select **Add me** to add the System Administrator role to your user. It might take around 30 minutes for the role to be reflected everywhere.

More details and options, see [Manage High-Privileged Admin Roles](/power-platform/admin/manage-high-privileged-admin-roles).

## Connect to your Azure Account

Before running any of the scripts below, you must log into your administrator account. To log in, run the following script:

```powershell
Connect-AzAccount
```

## General operations

1. To get the environment name for Copilot scheduled prompts, run the following script and connect with the admin account if requested:

```powershell
Get-AdminPowerAppEnvironment 'Microsoft 365'
```

Enter your display name (`Microsoft 365` by default). Note the `EnvironmentName` value will indicate your environment name.

2. You can also identify a user ID by running this script, using the appropriate user email (<user@domain.com> in the example below). Note the `Id` field value in the output and that will indicate the user’s ID:

```powershell
Connect-Entra  

Get-EntraUser -UserId 'user@domain.com'
```

## List Copilot scheduled prompts

There are different ways to run a script to list scheduled prompts created in your tenant.

### Get a list of Copilot scheduled prompts for the whole tenant

1. Get the `EnvironmentId` using the script provided earlier.
2. Run the following script, replacing the placeholder with your actual `EnvironmentId`, and connect with the admin account if prompted:

   ```powershell
   .\Get-CopilotActions.ps1 -EnvironmentId abc123-a100-xyz000-12345
   ```

   The list of Copilot scheduled prompts should display in the console.

### Get a list of Copilot scheduled prompts for a single user

1. Get the `EnvironmentId` and `UserId` using the scripts provided earlier.
2. Run the following script using the appropriate `EnvironmentId` and `UserId` to replace the placeholders below and connecting with admin account if requested:

   ```powershell
   .\Get-CopilotActions.ps1 -EnvironmentId abc123-a100-xyz000-12345 -UserId abc123-a100-xyz000-12345
   ```

   The list of Copilot scheduled prompts belonging to that user should display in the console.

### Export the list to an Excel/CSV file

Add the following to the end of the command:

```powershell
| Export-Csv -Path C:\temp\resultFile.csv
```

Example:

```powershell
.\Get-CopilotActions.ps1 -EnvironmentId abc123-a100-xyz000-12345 | Export-Csv -Path C:\temp\resultFile.csv
```

## Delete Copilot scheduled prompts

### Delete a single Copilot Action

1. Get the `EnvironmentId` and the `DataverseId` of the action you wish to delete.
2. Run the following script:

   ```powershell
   .\Remove-CopilotAction.ps1 -EnvironmentId abc123-a100-xyz000-12345 -DataverseId abc123-a100-xyz000-12345
   ```

## Delete multiple Copilot Scheduled Prompts from a single user

1. Complete Getting the Copilot Scheduled Prompts environment ID.
1. Complete Getting the Entra user object ID.
1. Run the following script using the appropriate `EnvironmentId` and `UserId` and connecting with admin account if requested:

   ```powershell
   .\Clear-CopilotActions.ps1 -EnvironmentId abc123-a100-xyz000-12345 -UserId abc123-a100-xyz000-12345
   ```
