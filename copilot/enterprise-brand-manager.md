---
title: Enterprise brand manager policy and organizational asset library (OAL) access
f1.keywords:
- NOCSH
ms.author: camillepack
author: camillepack
manager: scotv
ms.date: 05/14/2025
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

Your organization can enable their brand managers to set up and publish organization or official brand kits via [create.microsoft.com](https://create.microsoft.com). These brand kits can contain multiple logos, color palettes, fonts, images, and templates pertaining to a certain brand. Once published, the brand kit is available to all users in the organization on create.microsoft.com. They can use these brand kits to generate branded artifacts or manually add brand content to existing designs and images.

For this to happen, admins need to configure the Enterprise Brand Manager policy defining their group of brand managers who are responsible for creating, managing, and publishing the official or organizational brand kits.

Beyond brand kits, Copilot also supports access to an organization’s designated [organizational asset library (OAL)](/sharepoint/organization-assets-library). OALs provide broad, centralized access to brand content and support images, logos and illustrations. OALs need to be configured as searchable by an admin.

## Setting up Enterprise Brand Manager Policy

**Prerequisite** Create a security group with identified brand managers who will have access and permission to create, publish, and manage brand kits available to all users within the organization.

**Policy setup** Follow these steps to create and enable the Enterprise Brand Manager policy for your organization:

1. Navigate to [Config.office.com](https://config.office.com/) and sign in using an Administrator account.
1. Under Customization, select **Policy Management**.
1. Select your existing tenant level policy with scope set to **Apply to all users** or create a new tenant policy with scope set to **Apply to all users**.
1. Go to the **Policies** tab.
1. Use the search box to search for **Brand Manager**. Select the **Elevated role for Brand Managers** policy.
1. Set the policy to **Enabled**. By default, it's set as **Not configured**.
1. In the Security group email address field, provide the email address for the brand managers security group for your tenant.
1. Select **Apply**.

## Setting up an OAL to be accessible in the Create experience of the Microsoft 365 Copilot app

Connecting an OAL to Copilot enables brand content access in the Create experience of the Microsoft 365 Copilot app, while also enabling Copilot Chat access in PowerPoint and Word. To learn more, see [Connect organizational asset libraries to Copilot for an on-brand experience](/sharepoint/connect-organizational-asset-libraries-to-copilot)

Once the OAL has been provisioned, your entire organization will have access to the brand content from the designated OAL. This content can be found in Create in the Microsoft 365 Copilot app. You can edit an existing image and select the visuals pane to see `<tenant name>` assets.
