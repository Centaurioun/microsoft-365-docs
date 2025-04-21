---
title: Set up Microsoft 365 Copilot Chat pay-as-you-go
description: Learn how to set up pay-as-you-go billing for Microsoft 365 Copilot Chat.
ms.author: camillepack
author: camillepack
manager: scotv
ms.date: 04/21/2025
ms.reviewer: nishanair
audience: Admin
ms.topic: get-started
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- scotvorg
- m365copilot
- magic-ai-copilot
- essentials-overview
ms.custom: [copilot-learning-hub]
---

# Set up pay-as-you-go for Microsoft 365 Copilot Chat

Setting up the pay-as-you-go plan for Microsoft 365 Copilot Chat can be done directly from the Microsoft 365 admin center. This article provides step-by-step instructions on how to set up and manage pay-as-you-go billing.

## Prerequisites

To set up pay-as-you-go, you must have the following prerequisites:

- Azure subscription and resource group
  - You must have an owner or contributor Azure role to an Azure subscription to set up the pay-as-you-go service.
  - You must have an owner or contributor Azure role to an Azure resource group linked to the same Azure subscription to set up the pay-as-you-go service.
  - To learn more, see [Use the Azure portal and Azure Resource Manager to Manage Resource Groups](/azure/azure-resource-manager/management/manage-resource-groups-portal).
- One of the following administrator roles:
  - Global administrator
  - Billing administrator
  - AI administrator

## Steps to set up pay-as-you-go billing

### Add a Billing Policy
1. In the Microsoft 365 admin center, go to **Copilot** > **Billing & usage**.
2. On the "Billing policies" tab, select "Add a billing policy"
3. Select the Azure subscription, resource group, and region for the pay-as-you-go setup.
4. Select the user scope for the billing policy.
    - All Users: All users that are part of teh tenant will be part of billing policy
    - Specific group: Assign a specific security group to be part of the billing policy
5. Review details and click on the "Create policy" button to complete the creation on billing policy.

### Connect a Billing Policy to M365 Copilot Chat
1. Navigate to the "Pay-as-upi-go services" tab.
2. Select "M365 Copilot Chat" and choose the billing policy to connect to the Copilot service.

### Disable pay-as-you-go
Disabling pay-as-you-go for a Copilot service involves disconnecting the billing policies associated with the service such as "M365 Copilot Chat".
1. Navigate to the "Pay-as-you-go services" tab, and select the Copilot service such as "M365 Copilot Chat".
2. Unselect the billing policy, one at a time to disconnect the billing policy.
3. Read and accept the confirmation to complete the disconnection of the billing policy.

### Delete a Billing Policy
1. Select a billing policy and click on the "Delete billing policy" button.
2. Accept the confirmation dialogue. Any services connected to the billing policy will be disconnected.

> [!NOTE]
> When turning off pay-as-you-go, it may take up to two hours for users to stop being able to use the agents. Additionally, if the agent hasn't been used, it will no longer be accessible once pay-as-you-go is turned off.
   
### What if pay-as-you-go is already set up in the Power Platform admin center?

If you already set up pay-as-you-go in the Power Platform admin center, the two setups can coexist. You can also create another setup in the Microsoft 365 admin center without being double billed. The billing system ensures that you're only billed once for your user's usage, regardless of the setup location.

> [!NOTE]
> Although the setups can coexist, it's recommended to turn off pay-as-you-go in the Power Platform admin center before enabling it in the Microsoft 365 admin center.





## Next step

[View costs](view-cost.md) (article)
