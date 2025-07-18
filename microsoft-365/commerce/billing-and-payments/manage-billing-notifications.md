---
title: "Manage billing notifications and invoice attachment settings in the Microsoft 365 admin center"
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: smithk, ramagane
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.subservice: m365-commerce-management
ms.localizationpriority: medium
ms.collection: 
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_billing
- okr_SMB
- AdminSurgePortfolio
- admindeeplinkMAC
- GAUpdates
- campaignIDs-batch1
search.appverid:
- MET150
description: "Learn how to manage who receives billing notification emails and invoice attachments in the Microsoft 365 admin center."
ms.date: 04/01/2025
---

# Manage billing notifications and invoice attachment settings in the Microsoft 365 admin center

You can manage who receives billing notification emails for your organization on the **Billing notifications** page in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>. The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).

## Before you begin

- [Find out what type of billing account you have](../manage-billing-accounts.md#view-my-billing-accounts).
- If you have a Microsoft Customer Agreement (MCA) billing account type, you must be a Billing account owner or contributor to do the tasks in this article. For information about billing account roles, see [Understand your Microsoft business billing account](../manage-billing-accounts.md).
- If you have a Microsoft Online Services Agreement (MOSA), you must be a Global admin to do the tasks in this article. Billing admins can also make some of these changes, as noted in this article. For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).

[!INCLUDE [ga-roles-limitation](../../includes/ga-roles-limitation.md)]

> [!NOTE]
> If you're the person who signed up for the subscription, you're automatically a Billing account owner.

## Receive your organization's invoices as email attachments

You can choose to receive your organization's invoices as email attachments. However, the steps to manage the invoice attachment setting in the Microsoft 365 admin center depend on the type of billing account that you have. [Find out what type of billing account you have](../manage-billing-accounts.md#view-my-billing-accounts).

### Receive your invoice as an email attachment for MCA billing account types

If you have an MCA billing account type, the option to receive your invoice as an attachment to your invoice notification emails is linked with your billing profile. To turn on the invoice email attachment setting for a specific billing profile, use the following steps.

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Billing accounts</a> page.
1. On the **Overview** tab, select a billing account.
1. On the billing account details page, select the **Billing profiles** tab. The tab lists all billing profiles associated with the selected billing account.
1. Select a billing profile name to view its details page.
1. In the **Invoice and Billing Notifications** section, select **Manage settings** under **Invoice and payment contact settings**.
1. In the **Edit invoice and contacts settings** pane, under **Get invoices in email attachments**, switch the toggle to **On**.
1. If needed, add any additional recipient email addresses, then select **Save Changes**.

#### Manage accounts payable contacts

If you have an MCA billing account type and the default payment instrument is check or wire transfer, at least one Accounts payable contact is required. This contact receives copies of the invoice by email along with statements and payment inquiries. You have full control to add, edit, and delete Accounts payable contacts as needed. While the Billing group owner, contributor, and Invoice manager roles continue to receive invoice-ready emails and access invoices in the portals, they don't receive statements and payment reminders. If your default payment instrument isn't check or wire transfer, these contacts are optional.

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Billing accounts</a> page.
1. On the **Overview** tab, select a billing account.
1. On the billing account details page, select the **Billing profiles** tab. The tab lists all billing profiles associated with the selected billing account.
1. Select a billing profile name to view its details page.
1. In the **Invoice and Billing Notifications** section, under **Invoice and payment contact settings**, select **Manage settings**.
1. Select **Add account payable contact**.
1. Enter the required information and select **Save**.
1. The **Get invoices in email attachments** toggle is on by default so contacts get copies of the invoice.
1. If needed, add any additional recipient email addresses, then select **Save Changes**.

### Receive your invoice as an email attachment for MOSA billing account types

If you have an MOSA billing account type, the option to receive your invoice as an attachment to your invoice notification emails is managed on the **Billing  notifications** page in the Microsoft 365 admin center. To turn on the invoice email attachment setting on the **Billing notifications** page, use the following steps.

> [!NOTE]
> Billing admins can also do the following steps.

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.
1. Under **Billing notification settings**, select **Edit notification settings**.
1. In the **Billing notification settings** pane, under **Invoice PDF**, select the **Attach a PDF to your invoice emails** checkbox, then select **Save**.

To stop receiving the invoice attachment at any time, follow the steps in this procedure and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.

## Change who receives billing notifications

You can change who receives billing notifications for your organization in the Microsoft 365 admin center. However, the steps to change who receives billing notifications depend on the type of billing account that you have. [Find out what type of billing account you have](../manage-billing-accounts.md#view-my-billing-accounts).

### If you have an MCA billing account type

If you have an MCA billing account type, billing notification emails are sent to the primary email addresses for users who are assigned one of the following roles:

- Billing profile owner
- Billing profile contributor
- Invoice manager

To change the billing profile roles assigned to users, see [Assign billing profile roles](manage-billing-profiles.md#assign-billing-profile-roles).

To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).

#### Receive a copy of your invoice by email

You can receive a copy of your invoice attached as a pdf to your invoice ready email.  

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895">Billing accounts</a> page.
1. Select the Billing account that includes the Billing profile that you want to add email recipients to.
1. Select the **Billing profiles** tab.
1. Select the Billing profile that you want to update.
1. In the **Invoice and billing notifications**  section, select **Edit invoice and contact settings**.
1. Toggle the Edit invoice and contacts setting to **On**
1. Select **Save changes**

#### Add additional recipients

In case your primary email address isn't configured to receive emails, or if you want to receive the notifications at different email addresses, you can add them by using the following steps.

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895">Billing accounts</a> page.
2. Select the Billing account that includes the Billing profile that you want to add email recipients to.
3. Select the **Billing profiles** tab.
4. Select the Billing profile that you want to update.
5. In the **Invoice and billing notifications** - **Additional recipients** section, select **Edit recipients**.
6. In the **Additional recipients (optional)** text box, enter an email address that you want to add.
7. A box with the email address that you just entered appears. Select the box.
8. Repeat steps 6 and 7 for all the email addresses that you want to add.
9. Select **Save Changes**.

### If you have an MOSA billing account type

If you have an MOSA billing account type, billing notifications are sent to the primary and alternate email address of every Global and Billing admin in your organization. To change which users have the Global or Billing admin role, use the following steps.

#### Assign admin roles by using the Billing notifications page

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.
2. In the **Admins receiving Billing notifications** section, select **Change Billing admins** or **Change Global admins**. You can also choose to add a new account and assign one of the roles to it.
3. In the details pane, on the **Assigned** tab, select **Add users**.
4. In the **Add users** pane, type the user's display name or username, and then select the user from the list of suggestions.
5. Add multiple users until you're done.
6. Select **Add**, then close the pane.

#### Remove admin roles by using the Billing notifications page

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.
2. In the **Admins receiving billing notifications** section, select the **Change Billing admins** or **Change Global admins** link in the description text.
3. In the details pane, on the **Assigned** tab, select the users to remove from the role, and then select **Remove**.
4. In the confirmation box, select **Remove**, then close the pane.

## Change the language you receive email in

Billing notification emails are sent in your organization's preferred language. To change the preferred language, use the following steps.

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.
2. In the **Billing notification settings** section, select **Edit notification settings**.
3. In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.

## Change the email addresses for admins

You can change the primary email address of other admins in your organization. However, you can only change your own alternate email address, you can't change email addresses for other admins unless you have a global admin role

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.
2. In the **Admins receiving billing notifications** section, select a name.
3. In the right pane, add or update the primary and alternate email address as needed, then select **Save**.

## Change your organization's contact email

In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.

1. In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.
1. Under **Organization contact receiving billing notifications**, select the organization contact.
1. In the organization details pane, type the email address that you want to use, then select **Save**.

## Related content

[View your invoice in the Microsoft 365 admin center](view-your-bill-or-invoice.md) (article)\
[Billing information for Microsoft 365 for business in Mexico](mexico-billing-info.md) (article)\
[Understand your invoice for your Microsoft MCA billing account](understand-your-invoice.md) (article)\
[Understand your invoice for your Microsoft MOSA billing account](understand-your-invoice2.md) (article)
