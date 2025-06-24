---
title: Set up a budget for pay-as-you-go billing in Microsoft 365
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

# Set up a budget for pay-as-you-go billing in Microsoft 365

This article explains how to set spending limits for pay-as-you-go billing—currently available for Microsoft 365 Copilot services. This feature helps you monitor usage, receive alerts as costs approach budget thresholds, and plan more effectively.

Budgets are set at the billing policy level, not for individual users, agents, or sites. This means any limits or alerts apply to all services and users under that policy.

## Prerequisites

Before you begin, ensure you meet the following requirements:

- **Admin role**:

    - You must have either the [SharePoint Administrator](/entra/identity/role-based-access-control/permissions-reference#sharepoint-administrator) or [Global Administrator](/entra/identity/role-based-access-control/permissions-reference#global-administrator) role to access the Microsoft 365 admin center.

- **Permission levels**:
    - Users with Contributor access can view and edit budget settings.

    - Users with Reader access can view billing policies, but cannot see spending data or budget details.


Before you begin, ensure you have:

- [SharePoint Administrator](/entra/identity/role-based-access-control/permissions-reference#sharepoint-administrator) or [Global Administrator](/entra/identity/role-based-access-control/permissions-reference#global-administrator) role to access the Microsoft 365 admin center.

- Contributor access to view and edit budget settings. Users with reader access can view billing policies but not spending data or budget details. [Learn more about admin roles](/microsoft-365/admin/add-users/about-admin-roles).

## Set up a budget

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home).

2. Go to **Copilot** > **Billing & usage**.

3. On the **Billing policies** tab, select the policy you want to manage.

4. On the policy panel, select the **Budget** tab.

5. Select **Spending** to view current expenses for services linked to the policy.

    > [!NOTE]
    > There can be up to a four-hour delay before consumption data appears in the graph.

6. Select **Settings** to configure your budget and alert preferences.

    a. Select the **Set limits for this billing policy** checkbox.

    b. Under **Budget**, enter the dollar amount for your spending limit.

    c. Under **Reset the budget**, select when you want to reset he budget.

    - Monthly (resets on the first day of each month)
    - Quarterly (resets on January 1, April 1, July 1, and October 1)
    - Yearly (resets on January 1)

    d. Under **Send email alerts** (optional):

    - Add recipients (only [mail-enabled security groups](/exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups) are currently supported).

    - Set the budget percentage that triggers alerts.

        - If selected, 100% is enabled by default.

        - You can add up to four additional thresholds (0–99%).

    > [!NOTE]
    > Email alerts can be delayed by up to 24 hours. Alerts are currently sent from Azure but will transition to the Microsoft 365 admin center in a future release.

7. Select **Save** to apply your budget settings.

    > [!IMPORTANT]
    > The only way to stop billing is to [disconnect the payment method](pay-as-you-go-setup-copilot#disconnect-pay-as-you-go-billing). Reaching 100% of your budget doesn't stop the service or billing.



<!---
    > [!NOTE]
    > You can currently select only mail-enabled security groups to receive alerts. [Learn how to create a mail-enabled security group](/exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups).
    > 
    > There can be up to a 24-hour delay before email alerts are sent after a budget threshold is reached.
    > 
    > Budget email alerts are currently sent from Azure. However, you can still view and manage your budget in the Microsoft 365 admin center. This behavior will be updated in a future release so that alerts are sent directly from the admin center.

    d. Under **Send email alerts**, you can add recipients to receive budget notifications and set the budget percentage that will trigger an alert.

    > [!NOTE]
    > You can currently select only mail-enabled security groups to receive alerts. [Learn how to create a mail-enabled security group](/exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups).
    > 
    > There can be up to a 24-hour delay before email alerts are sent after a budget threshold is reached.
    > 
    > Budget email alerts are currently sent from Azure. However, you can still view and manage your budget in the Microsoft 365 admin center. This behavior will be updated in a future release so that alerts are sent directly from the admin center.
--->


<!---

    > [!NOTE]
    > You can currently select only mail-enabled security groups to receive alerts. [Learn how to create a mail-enabled security group](/exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups).

    > [!NOTE]
    > There can be up to a 24-hour delay before email alerts are sent after a budget threshold is reached.

    > [!NOTE]
    > Budget email alerts are currently sent from Azure. However, you can still view and manage your budget in the Microsoft admin center. This behavior will be updated in a future release so that alerts are sent directly from the admin center.


    - Add recipients to receive budget notifications.

        - You can currently select only mail-enabled security groups to receive alerts. [Learn how to create a mail-enabled security group](/exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups).

        - There can be up to a 24-hour delay before email alerts are sent after a budget threshold is reached.

        - Budget email alerts are currently sent from Azure. However, you can still view and manage your budget in the Microsoft 365 admin center. This behavior will be updated in a future release so that alerts are sent directly from the admin center.



> [!NOTE]
> This feature is currently available only for Microsoft 365 Copilot services. Other services will be added in future releases.

--->
