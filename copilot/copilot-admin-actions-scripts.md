---
title: "Copilot Actions admin scripts guide"
author: camillepack
ms.author: camillepack
manager: dansimp
ms.service: microsoft-365-copilot
ms.topic: include
description: Learn about using Copilot Actions admin scripts and the prerequisites and steps for various operations.
ms.date: 05/15/2025
ROBOTS: NOINDEX, NOFOLLOW
---

# Copilot Actions admin scripts guide

## Prerequisites

### General Prerequisites

- Have the Global Administrator and Power Platform Administrator roles assigned to your user in Azure portal for the tenant on which you want to do operations.
- Use [PowerShell v7.0+](/powershell/scripting/install/installing-powershell)
- Have `Az.Accounts` and `Microsoft.PowerApps.Administration.PowerShell` [modules installed](/powershell/module/powershellget/install-module).
- Have all scripts in the same folder and run the scripts while being in that folder.

### Getting System Administrator role on Copilot Actions environment

- Go to [Power Platform Admin Center](https://admin.powerplatform.microsoft.com/environments).
- Find the **Microsoft 365** environment and select it. (This is the default name for Copilot Actions environment; some tenants might use a different name).
- Select **Membership**.
- Select **Add me** to add the System Administrator role to your user. It might take around 30 minutes for the role to be reflected everywhere.

More details and options, see [Manage High-Privileged Admin Roles](/power-platform/admin/manage-high-privileged-admin-roles).

### Connect to your Azure Account

Before running any of the scripts below, log into your administrator account. You don't need to complete this step again if you keep the PowerShell console open.

1. Run the following script:

```powershell
Connect-AzAccount
```

1. Connect with your administrator account.
1. Run any of the scripts listed later.

## General operations

Some operations are required in multiple scripts, this section explains how to accomplish those.

### Getting the Copilot Actions environment ID

1. Determine what the environment name is for the Copilot Actions. It is “Microsoft 365” by default.
1. Run

```powershell
Get-AdminPowerAppEnvironment 'Microsoft 365'
```

Connect with admin account if requested.

1. Note the **EnvironmentName** value.

### Getting the Microsoft Entra user object ID

1. Run  

```powershell
Connect-Entra
```

Connect with admin account.

2. Run the following script, using the appropriate UserId

```powershell
Get-EntraUser -UserId '<user@domain.com>'
```

Note the value from the **Id** field.

## List Copilot Actions

There are different ways to run the script:

1. Get the list of Copilot Actions for the whole tenant:

    a. Complete Getting the Copilot Actions environment ID
    b. Run the following script, using the appropriate EnvironmentId

    ```powershell
    .\Get-CopilotActions.ps1 -EnvironmentId ecd91bb5-a790-4db6-8021-0c21c483269f
    ```

    Connect with admin account if requested.
    c. The list of Copilot Actions should display in the console.

2. Get the list of Copilot Actions for a single user:

    a. Complete Getting the Copilot Actions environment ID.
    b. Complete Getting the Microsoft Entra user object ID.
    c. Open a PowerShell shell.
    d. Run the following script, using the appropriate EnvironmentId and UserId.

   ```powershell
   .\Get-CopilotActions.ps1 -EnvironmentId ecd91bb5-a790-4db6-8021-0c21c483269f -UserId 1a8031b4-ba57-4ee7-bed2-99fea3081d9d
   ```
    Connect with admin account if requested.
    e. The list of Copilot Actions belonging to that user should be displayed in the console

3. Get the list of Copilot Actions output to an Excel/CSV file:

    a. Follow 1. or 2. listed previously depending on the scenario you’re interested in, but adding

    ```powershell
        | Export-Csv -Path C:\temp\resultFile.csv
    ```

    at the end of the `.\Get-CopilotActions.ps1` command.

    b.For example, the command from 1. would become  

    ```powershell
    .\Get-CopilotActions.ps1 -EnvironmentId ecd91bb5-a790-4db6-8021-0c21c483269f | Export-Csv -Path C:\temp\resultFile.csv
    ```

## Delete a single Copilot Action

1. Complete `Getting the Copilot Actions environment ID`.
1. Follow List Copilot Actions and note the `DataverseId` of the Action you want to delete.
1. Run the following script, using the appropriate `EnvironmentId` and `DataverseId`

    ```powershell
    .\Remove-CopilotAction.ps1 -EnvironmentId ecd91bb5-a790-4db6-8021-0c21c483269f -DataverseId 18ebd469-6747-409b-8f10-1299e7294074
    ```

    Connect with admin account if requested.

## Delete multiple Copilot Actions from a single user

1. Complete `Getting the Copilot Actions environment ID`.
1. Complete `Getting the Microsoft Entra user object ID`
1. Run the following script, using the appropriate `EnvironmentId` and `UserId`.

    ```powershell
    .\Clear-CopilotActions.ps1 -EnvironmentId ecd91bb5-a790-4db6-8021-0c21c483269f -UserId 1a8031b4-ba57-4ee7-bed2-99fea3081d9d
    ```

    Connect with admin account if requested.

## Delete Copilot Actions (advanced)

Note that the output of `Get-CopilotActions.ps1` can be used as the input to `Remove-CopilotAction.ps1`, resulting in the deletion of all Actions reaching `Remove-CopilotAction.ps1`. This allows for custom filtering. For example, to only consider action of a certain type:

```powershell
.\Get-CopilotActions.ps1 -EnvironmentId ecd91bb5-a790-4db6-8021-0c21c483269f `

| Where-Object { $_.BotType -eq "Prepare" } `

|.\Remove-CopilotAction.ps1
```
