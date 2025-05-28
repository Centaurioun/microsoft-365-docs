---
title: Set up or disconnect pay-as-you-go services in Microsoft 365
ms.author: chucked
author: chuckedmonson
manager: jtremper
ms.reviewer: siruvanti
ms.date: 05/30/2025
audience: admin
ms.topic: install-set-up-deploy
ms.service: microsoft-365-business
ms.subservice:
search.appverid: 
ms.collection: 
ms.localizationpriority:  medium
description: Learn how to set up or disconnect billing for pay-as-you-go services in Microsoft 365.
---

# Set up or disconnect pay-as-you-go services in Microsoft 365

## Set up pay-as-you-go services

Setting up pay-as-you-go services for Microsoft Syntex and Microsoft Copilot involves different processes but shares the same prerequisites.

### Prerequisites

Before setting up pay-as-you-go services, ensure you have the following information:

- An Azure subscription in the same tenant as Microsoft 365.

- An Azure resource group in that subscription.

- Appropriate admin roles: Global Administrator for accessing the Microsoft 365 admin center, and Owner or Contributor rights to the Azure subscription and resource group.

To set up a pay-as-you-go service for Microsoft Syntex, follow the [steps for Microsoft Syntex](#setup-guide-for-microsoft-syntex). To set up a pay-as-you-go service for Microsoft 365 Copilot, follow the [steps for Microsoft 365 Copilot](#set-guide-for-microsoft-365-copilot).

### Setup guide for Microsoft Syntex

#### Step 1: Access the Microsoft 365 admin center

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home).

2. Go to the **Setup** section, and then go to **Billing and licenses**.

#### Step 2: Activate pay-as-you-go services

1. In the **Billing and licenses** section, select **Activate pay-as-you-go services**.

2. On the **Activate pay-as-you-go services** page, select **Get started** to begin the setup process.

#### Step 3: Configure billing

1. On the **Pay-as-you-go services** page, select the service you want to set up (for example, **SharePoint Agents** or **Syntex services**).

2. On the **Set up billing and turn on services** panel, choose your Azure subscription, resource group, and region.  

3. Read and accept the pay-as-you-go terms of service.

4. Select **Save** to complete the setup.

### Set guide for Microsoft 365 Copilot

#### Step 1: Set up a billing policy

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home), select **Copilot**, and then select **Billing & usage**.

2. On the **Billing & usage** page, select **Add a billing policy**.

3. On the **Billing details** page, fill in required information, including the policy name, the Azure subscription name, resource group, and region. (The region determines where your tenant ID and usage information such as site names are stored.)

4. Read and accept the pay-as-you-go billing terms of service.

5. Check the box to accept the pay-as-you-go billing terms of service. Then select **Next**.

6. On the **Users** page, choose to apply this policy to either **All users** or a **Specific group**. If you select **Specific group**, you can then search and add a single group for the policy.

7. Select **Next**.

8. On the **Review and finish** page, review all the information. If it looks good, select **Create policy**.

    Your billing policy is now created.

#### Step 2: Connect the billing policy to a pay-as-you-go service

You can then connect this new billing policy to a pay-as-you-to service by selecting the **Connect a service** link on the **Billing & usage** page.

## Monitor usage and costs

Once the setup is complete, you can monitor your pay-as-you-go usage and costs in Microsoft Cost Management for Azure. Ensure you have at least read access to the resource group specified for billing.

## Disconnect pay-as-you-go services

### Prerequisites

Ensure you have the necessary admin roles (Global Administrator or SharePoint Administrator) and Owner or Contributor rights to the Azure subscription and resource group.

### Step-by-step disconnection guide

#### Step 1: Access the Microsoft 365 admin center

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home).

2. Go to the **Settings** section, and then select **Org settings**.

#### Step 2: Manage billing

1. On the **Org settings** page, select **Pay-as-you-go services**.

2. On the **Pay-as-you-go services** page, select the service you want to disconnect (for example, **SharePoint Agents** or **Syntex services**).

3. On the **Manage billing** panel, select **Edit billing information**.

#### Step 3: Disconnect Azure subscription

1. Under **Manage billing**, select **Disconnect Azure subscription**.

2. Confirm the disconnection by selecting **Disconnect** on the confirmation window.

#### Step 4: Review billing and usage

After disconnecting the service, review your billing and usage to ensure all charges are accurate and no further usage is being billed to the Azure subscription.

For detailed instructions about how to set up and disconnect specific pay-as-you-go services, see the service-specific get started documentation.
