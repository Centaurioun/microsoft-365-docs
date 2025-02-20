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

## Set Up pay-as-you-go services

### Prerequisites

Before setting up pay-as-you-go services, ensure you have the following:

An Azure subscription in the same tenant as Microsoft 365.

An Azure resource group in that subscription.

Appropriate admin roles: Global Administrator for accessing the Microsoft 365 admin center, and Owner or Contributor rights to the Azure subscription and resource group.

### Step-by-step setup guide

Access the Microsoft 365 Admin Center:

Sign in to the Microsoft 365 admin center.

Navigate to the Setup section and select Billing and licenses.

Activate Pay-as-you-go Services:

In the Billing and licenses section, select Activate pay-as-you-go services.

Click on Get started to begin the setup process.

Configure Billing:

On the Pay-as-you-go services page, select the service you want to set up (for example, Syntex, Copilot, or Microsoft 365 Backup).

On the Set up billing and turn on services panel, choose your Azure subscription, resource group, and region.  

Read and accept the pay-as-you-go terms of service.

Click Save to complete the setup.

Monitor Usage and Costs:

Once the setup is complete, you can monitor your PAYG usage and costs in Microsoft Cost Management for Azure. Ensure you have at least read access to the resource group specified for billing.

## Disconnect pay-as-you-go services

### Prerequisites

Ensure you have the necessary admin roles (Global Administrator or SharePoint Administrator) and Owner or Contributor rights to the Azure subscription and resource group.

### Step-by-step disconnection guide

Access the Microsoft 365 Admin Center:

Sign in to the Microsoft 365 admin center.

Navigate to Settings > Org settings.

Manage Billing:

On the Pay-as-you-go services page, select the service you want to disconnect (e.g., Syntex, Copilot, SharePoint Agents). 

On the Manage billing panel, select Edit billing information.

Disconnect Azure Subscription:

Under Manage billing, select Disconnect Azure subscription.

Confirm the disconnection by selecting Disconnect on the confirmation window.

Review Billing and Usage:

After disconnecting the service, review your billing and usage to ensure all charges are accurate and no further usage is being billed to the Azure subscription.

 
For detailed instructions on setting up and disconnecting specific Pay as you go services, please refer to the product-specific get started documentation.
