---
# Required metadata
# For more information, see https://learn.microsoft.com/en-us/help/platform/learn-editor-add-metadata
# For valid values of ms.service, ms.prod, and ms.topic, see https://learn.microsoft.com/en-us/help/platform/metadata-taxonomies

title: Enriching and customizing your organization's profile cards
description: Microsoft Learn page telling admins how to customize their organization's profile cards by adding and removing properties that can be enriched from external systems
author:      SuryaLashmiS # GitHub alias
ms.author:   srinivasansu # Microsoft alias
ms.service: microsoft-365-admin
ms.topic: how-to
ms.date:     07/24/2025
---

# Enriching and customizing your organization's profile cards 

[Profile cards](https://support.microsoft.com/en-us/office/profile-cards-in-microsoft-365-e80f931f-5fc4-4a59-ba6e-c1e35a85b501) in Microsoft 365 show key information about an organization’s employees. As an admin, you can use the Microsoft 365 admin center to add certain properties from your organization's profile cards. These settings are configured under People settings in your admin dashboard.

## Before you begin

You must be a Global Administrator or a People Administrator to do the tasks in this article. For more information, see [About admin roles](../add-users/about-admin-roles.md).

## Properties in profile cards

Profile card properties map to attributes in the [Microsoft 365 profile resource](/graph/api/resources/profile?view=graph-rest-beta) and can be populated from various sources, including:  

- [Microsoft Entra ID](/entra/fundamentals/how-to-manage-user-profile-info)

- [Organizational data in Microsoft 365](/entra/fundamentals/how-to-manage-user-profile-info)

- [Microsoft 365 Copilot connectors for people data](/graph/peopleconnectors)

- User-provided details

Read Build Microsoft 365 Copilot connectors for people data to learn how to ingest people data from your external source systems (for example human resources, talent management, or other people systems) into Microsoft Graph.

### Default properties

Some properties are shown by default on profile cards when data is available. These properties can't be removed by admins:

- Name

- Email

- Chat

- Work phone

- Mobile

- Work location

- Company

- Job title

- Department

- Business address

### Optional properties

### Change your country/region

You can't change the country/region for your subscription. The country/region where your organization is headquartered determines which services are available to you, the taxes and billing currency, and the location of the data center. To change your organization's country/region, sign up for a new account, choose the desired country or region, and buy a new subscription.

### Edit organization information

To change information on your organization's profile page, use the following steps.
  
1. Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a>.
2. In the **Navigation menu**, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**Org settings**</a> page.
3. Select the **Organization profile** tab, select **Organization information**.
4. Update your organization's information, then select **Save**. You must fill in all required fields marked with an asterisk (*) before you can save your changes.

> [!NOTE]
> SharePoint Online and OneDrive have a 256-character limit on Windows PCs. If you exceed the character limit, you receive an error message when you try to do anything within the synchronized document libraries, like creating folders or renaming documents.

### What do the organization information fields mean?

The following table explains the fields shown in the **Organization information** pane.

| Field | Description |
|---------|---------|
|Name  | The organization's name that's used to identify it.  |
|Address, City, State/Province, ZIP/Postal code   | The address entered is shown on your invoice under **Sold To**. The Sold To address is the same as your organization address on your profile page.    |
|Country or region   | The country/region where the organization is headquartered. The selected country/region determines which services are available to you, the taxes and billing currency for your country/region, and the location of the data center closest to you. To find out whether a country/region is supported, see [About license restrictions](https://www.microsoft.com/microsoft-365/business/microsoft-office-license-restrictions).<br/><br/>**NOTE:** After you select a country/region, it can't be changed. If you need to change the selection, you must cancel your subscription and sign up again. For help with this process, [contact support](../get-help-support.md).        |
|Phone   | The primary telephone number for your organization. It's usually the number of your organization headquarters.  |
|Technical contact | The email address for the primary technical person who administers your subscription. This person receives communications about Microsoft service status. |
|Preferred language | Determines the language for all communications that are sent from Microsoft to your organization. When you sign up, this setting determines the language used by SharePoint Online, that your users see on your team site. If you change the language preference setting after you sign up, all future communications are sent in the most recent language selected.<br/><br/>**IMPORTANT:** The language used by SharePoint Online can't be changed.           |

## Change your contact preferences for communications from Microsoft

Use the **Contact preferences** section of the Settings & privacy page to choose the Microsoft 365 product-related communications that you want to receive.
  
Read [Update your admin phone number and email address in Microsoft 365](update-phone-number-and-email-address.md) for info on how to change your admin cell phone number and email address.
  
### To update your information
  
1. In the admin center, select the **Settings** icon in the top right of the header.

2. Select **Update contact preferences**.

3. Under **Contact preferences**, choose the types of product-related communications you want to receive.

4. Choose **Save** when you're done.
  
For Office 365 Enterprise, Microsoft 365 Business Standard, and Microsoft 365 Business Basic, when you first signed up as an admin for Microsoft 365, depending on the country or region of the users in your organization, your users might be automatically signed up to receive product-related communications.

## Change organization settings for Cloud PCs

By default, new Cloud PCs are created with the Windows 11 operating system and the Standard User account type. To change these default settings, use the following steps.

1. In the Microsoft 365 admin center, in the **Navigation menu**, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**Org settings**</a> page.
2. On the **Services** tab, select **Windows 365**.
3. Select your preferred operating system and account type, then select **Save**.

Organization settings only apply to newly created Cloud PCs. When these settings are changed, they don't change the OS or account type of existing Cloud PCs.

## Related content

[Update your Microsoft 365 admin phone number and email address](update-phone-number-and-email-address.md) (article)\
[Send email from a different address in Outlook.com](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (article)\
[Change a user name and email address](../add-users/change-a-user-name-and-email-address.md) (article)\
[Configure email forwarding in Microsoft 365](../email/configure-email-forwarding.md) (article)
