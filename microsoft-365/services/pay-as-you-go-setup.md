---
title: Set up or disconnect pay-as-you-go services in Microsoft 365
ms.author: siruvanti
author: tbd
manager: snaray
ms.reviewer: 
ms.date: 02/20/2025
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

### Prerequisites

Before setting up pay-as-you-go services, ensure you have the following information:

- An Azure subscription in the same tenant as Microsoft 365.

- An Azure resource group in that subscription.

- Appropriate admin roles: Global Administrator for accessing the Microsoft 365 admin center, and Owner or Contributor rights to the Azure subscription and resource group.

### Step-by-step setup guide

#### Step 1: Access the Microsoft 365 admin center

a. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home).

b. Go to the **Setup** section, and then go to **Billing and licenses**.

#### Step 2: Activate pay-as-you-go services

a. In the **Billing and licenses** section, select **Activate pay-as-you-go services**.

b. On the **Activate pay-as-you-go services** page, select **Get started** to begin the setup process.

#### Step 3: Configure billing

a. On the **Pay-as-you-go services** page, select the service you want to set up (for example, **Agents in SharePoint** or **Syntex services**).

b. On the **Set up billing and turn on services** panel, choose your Azure subscription, resource group, and region.  

c. Read and accept the pay-as-you-go terms of service.

d. Select **Save** to complete the setup.

#### Step 4: Monitor usage and costs

Once the setup is complete, you can monitor your pay-as-you-go usage and costs in Microsoft Cost Management for Azure. Ensure you have at least read access to the resource group specified for billing.

## Disconnect pay-as-you-go services

### Prerequisites

Ensure you have the necessary admin roles (Global Administrator or SharePoint Administrator) and Owner or Contributor rights to the Azure subscription and resource group.

### Step-by-step disconnection guide

#### Step 1: Access the Microsoft 365 admin center

a. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home).

b. Go to the **Settings** section, and then select **Org settings**.

#### Step 2: Manage billing

a. On the **Org settings** page, select **Pay-as-you-go services**.

b. On the **Pay-as-you-go services** page, select the service you want to disconnect (for example, **Agents in SharePoint** or **Syntex services**).

c. On the **Manage billing** panel, select **Edit billing information**.

#### Step 3: Disconnect Azure subscription

a. Under **Manage billing**, select **Disconnect Azure subscription**.

b. Confirm the disconnection by selecting **Disconnect** on the confirmation window.

#### Step 4: Review billing and usage

After disconnecting the service, review your billing and usage to ensure all charges are accurate and no further usage is being billed to the Azure subscription.

For detailed instructions on setting up and disconnecting specific pay-as-you-go services, see the product-specific get started documentation.
