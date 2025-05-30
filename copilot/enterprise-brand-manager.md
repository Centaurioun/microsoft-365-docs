---
title: Enterprise brand manager policy and organizational asset library (OAL) access
f1.keywords:
- NOCSH
ms.author: camillepack
author: camillepack
manager: scotv
ms.date: 05/30/2025
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- Tier2
- scotvorg
- M365-subscription-management 
- Adm_O365
- Adm_TOC
- m365copilot
- magic-ai-copilot
description: "Learn about enabling brand kits and asset libraries in the Microsoft 365 Copilot app to streamline on-brand content creation."
---

# Enterprise brand manager policy and organizational asset library (OAL) access

Your organization can enable their brand managers to set up and publish organization or official brand kits via [create.microsoft.com](https://create.microsoft.com). These brand kits can contain multiple logos, color palettes, fonts, images, and templates pertaining to a certain brand.

Once published, the brand kit is available to all users in the organization on create.microsoft.com. They can use these brand kits to generate branded artifacts or manually add brand content to existing designs and images.

To enable this functionality, admins must configure the Enterprise Brand Manager policy, which involves:

- Defining a security group that includes the brand managers.
- Assigning responsibility to these brand managers for creating, managing, and publishing the official or organizational brand kits.

Beyond brand kits, Copilot also supports access to an organization’s designated [organizational asset library (OAL)](/sharepoint/organization-assets-library). OALs provide broad, centralized access to brand content and support images, logos and illustrations. OALs need to be configured as searchable by an admin.

## Setting up Enterprise Brand Manager policy

**Prerequisite** Create a security group with identified brand managers who have access and permission to create, publish, and manage brand kits available to all users within the organization.

**Policy setup** Follow these steps to create and enable the Enterprise Brand Manager policy for your organization:

1. Navigate to [Config.office.com](https://config.office.com/) and sign in using an Administrator account.
1. Under Customization, select **Policy Management**.
1. Select your existing tenant level policy with scope set to **Apply to all users** or create a new tenant policy with scope set to **Apply to all users**.
1. Go to the **Policies** tab.
1. Use the search box to search for **Brand Manager**. Select the **Elevated role for Brand Managers** policy.

    :::image type="content" source="media/brand-manager/brand-manager-policy.png" alt-text="Screenshot showing the Policy Management page to configure settings." lightbox="media/brand-manager/brand-manager-policy.png":::

6. Set the policy to **Enabled**. By default, it's set as **Not configured**.
7. In the Security group email address field, provide the email address for the brand managers security group for your tenant.

    :::image type="content" source="media/brand-manager/brand-manager-role.png" alt-text="Screenshot showing the Security group email text box filled with an email." lightbox="media/brand-manager/brand-manager-role.png":::

8. Select **Apply**.

## Setting up an OAL to be accessible in the *Create* experience of the Microsoft 365 Copilot app

Connecting an OAL to Copilot enables brand content access in the **Create** experience of the Microsoft 365 Copilot app, while also enabling Copilot Chat access in PowerPoint and Word.

:::image type="content" source="media/brand-manager/brand-manager-create.png" alt-text="Screenshot showing the Microsoft 365 Copilot Create tab with an image generated.":::

To learn more, see [Connect organizational asset libraries to Copilot for an on-brand experience](/sharepoint/connect-organizational-asset-libraries-to-copilot).

### What happens after setup

Once the OAL is provisioned and configured as searchable by an admin, the following capabilities become available to your organization:

- **Organization-wide access to brand content**
All users in your tenant can browse and use the brand assets stored in the designated OAL. These assets include logos, illustrations, and other approved visuals that support your brand identity.

- **Seamless integration in the *Create* experience**
Within the Microsoft 365 Copilot app, users can access these assets directly from the **Create** tab. The integration makes it easy to incorporate brand visuals into new content without needing to search external sources or local folders.

- **Visuals pane support for editing images**
When editing an image in the Create experience, users can open the **Visuals** pane to explore available assets. The visuals appear under a label that reflects your tenant name, making it clear that the content is organization-approved.
