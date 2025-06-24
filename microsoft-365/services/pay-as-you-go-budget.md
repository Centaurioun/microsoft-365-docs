---
title: Set a budget for pay-as-you-go billing in Microsoft 365
ms.author: chucked
author: chuckedmonson
manager: jtremper
ms.reviewer: ivchenya
ms.date: 06/25/2025
audience: admin
ms.topic: install-set-up-deploy
ms.service: microsoft-365-business
ms.subservice:
search.appverid: 
ms.collection: 
ms.localizationpriority:  medium
description: Learn how to set up a billing budget for pay-as-you-go services in Microsoft 365.
---

# Set a budget for pay-as-you-go billing in Microsoft 365

> [!NOTE]
> This feature is currently available only for Microsoft 365 Copilot services. Other services will be added in future releases.

This article explains how to set up a budget for pay-as-you-go billing in Microsoft 365.

## Prerequisites

Before you begin, ensure you have the following roles:

- [SharePoint Administrator](/entra/identity/role-based-access-control/permissions-reference#sharepoint-administrator) or [Global Administrator](/entra/identity/role-based-access-control/permissions-reference#global-administrator) for accessing the Microsoft 365 admin center.

- Contributor access to view and edit budget settings. Users with reader access can view billing policies but not spending data or budget details. [Learn more about admin roles](/microsoft-365/admin/add-users/about-admin-roles).

## Set up a budget

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home).

2. Go to **Copilot** > **Billing & usage**.

3. On the **Billing policies** tab, select the policy for which you want to set a budget.

4. On the policy panel, select the **Budget** tab.

5. Select **Spending** to view and monitor your expenses for the services linked to the billing policy.

    > [!NOTE]
    > There might be up to a four-hour delay before consumption data appears in the graph.

6. Select **Settings** to set a budget and specify who to notify when the cost of the services using the policy reaches the specified percentage of your budget.

    a. Select the **Set limits for this billing policy** checkbox.

    b. Under **Budget**, enter the dollar amount you want to be the limit.

    c. Under **Reset the budget**, select when you want the budget to reset.

    d. Under **Send email alerts**, you can add recipients to receive budget notifications and set the budget percentage that will trigger an alert.

    > [!NOTE]
    > • You can currently select only mail-enabled security groups to receive alerts. [Learn how to create a mail-enabled security group](/exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups).
    > 
    > • There can be up to a 24-hour delay before email alerts are sent after a budget threshold is reached.
    > 
    > • Budget email alerts are currently sent from Azure. However, you can still view and manage your budget in the Microsoft 365 admin center. This behavior will be updated in a future release so that alerts are sent directly from the admin center.

<!---

    > [!NOTE]
    > You can currently select only mail-enabled security groups to receive alerts. [Learn how to create a mail-enabled security group](/exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups).

    > [!NOTE]
    > There can be up to a 24-hour delay before email alerts are sent after a budget threshold is reached.

    > [!NOTE]
    > Budget email alerts are currently sent from Azure. However, you can still view and manage your budget in the Microsoft admin center. This behavior will be updated in a future release so that alerts are sent directly from the admin center.
--->

7. Select **Save** to apply your budget settings.

    > [!IMPORTANT]
    > The only way to stop billing is to [disconnect the payment method](pay-as-you-go-setup-copilot#disconnect-pay-as-you-go-billing). Reaching 100% of your budget doesn't stop the service or billing.
