---
title: Overview of Copilot Pages and Copilot Notebooks storage
ms.author: jenz
author: jenzamora
manager: jtremper
audience: Admin
ms.topic: article
ms.service: loop
ms.reviewer: michalbr, dancost
ms.date: 06/10/2025
ms.localizationpriority: medium
search.appverid: MET150
ms.collection: 
- M365-collaboration
- essentials-compliance
- magic-ai-copilot
description: Learn about Copilot Pages and Copilot Notebooks storage in the Microsoft 365 ecosystem.
f1.keywords:
- CSH
ms.custom: 
- NewAdminCenter_Update
- chat-teams-channels-revamp
appliesto: 
- Microsoft Teams
---

# Overview of Copilot Pages and Copilot Notebooks storage

## Storage

Copilot Pages and Copilot Notebooks are stored within your tenant in SharePoint Embedded. Copilot Pages, Copilot Notebooks and the Loop My workspace all use the same container. The container is lifetime managed with the user account and can be [managed using SharePoint Embedded admin tools](cpcn-loop-spe-management.md).

## Container name

The Copilot Pages, Copilot Notebooks and Loop My workspace all use the same container. This user-owned container is named 'Pages' if the person visits the M365 Copilot app first. It is named 'My workspace' if the person visits the Loop app first. To get a list of all of these user-owned containers in your organization, regardless of the container name, update the following sample PowerShell to your needs:

```PowerShell
Get-SPOContainer -OwningApplicationId 'a187e399-0c36-4b98-8f04-1edc167a0996' | WHERE OwnershipType -EQ 'UserOwned' | FT
```

## Storage quota

All Copilot Pages and Copilot Notebooks count against your tenant's SharePoint storage quota.

SharePoint Embedded also offers a platform for developers to build their own applications. This alternate usage pattern which bills per use is different from Loop and Copilot Pages storage quota management.

## Storage limits

Copilot Pages + Copilot Notebooks container has a maximum size of 25 TB. This limit can't be increased or decreased. Learn more about [SharePoint Embedded container limits](/sharepoint/dev/embedded/concepts/app-concepts/limits-calling).

## Storage management after user departure

- [Copilot Pages](#copilot-pages) and [Copilot Notebooks](#copilot-notebooks) store content within the same user-owned SharePoint Embedded container.
- This personal content is private by default, allowing users to work without forced sharing or coauthoring, similar to OneDrive.

### Copilot Pages

- Copilot Pages are stored in a user-owned SharePoint Embedded container, created by Copilot. The container is lifecycle managed with the user account, deleted when the user account is deleted from the organization.
- Copilot Pages can't be permanently reassigned to a new owner. It follows the same cleanup schedule as OneDrive: 30 days active, then soft deleted, and permanently purged 93 days after soft deletion.
- Admins can recover content during the soft delete period using the SharePoint Admin Center or PowerShell.

> [!NOTE]
> When a user selects the Copilot Pages module in the Microsoft 365 Copilot app, a SharePoint Embedded container is currently created automatically—even if the user does not go on to create a Copilot Page. If no files are added to the container, the system will later delete it automatically. *This behavior is temporary.* An update is in progress to ensure that a Copilot Pages container is only created when a user actually creates a Copilot Page. Until that update is deployed, IT administrators and compliance officers can safely disregard these system-initiated deletions. These containers do not contain any user-generated content when they are removed.

> [!IMPORTANT]
> A feature for IT admins to assign temporary custodians during the cleanup period of user-owned workspaces isn't yet available. This capability for Copilot Pages and Copilot Notebooks is planned (Microsoft Roadmap ID 421612).

### Copilot Notebooks

- Copilot Notebooks are stored in a user-owned SharePoint Embedded container, created by Copilot. The container is lifecycle managed with the user account, deleted when the user account is deleted from the organization.
- Copilot Notebooks can't be permanently reassigned to a new owner. It follows the same cleanup schedule as OneDrive: 30 days active, then soft deleted, and permanently purged 93 days after soft deletion.
- Admins can recover content during the soft delete period using the SharePoint Admin Center or PowerShell.

> [!IMPORTANT]
> A feature for IT admins to assign temporary custodians during the cleanup period of user-owned workspaces isn't yet available. This capability for Copilot Pages and Copilot Notebooks is planned (Microsoft Roadmap ID 421612).

## Related topics

- [Summary of Compliance, Lifecycle, Governance](cpcn-compliance-summary.md)
- [Requirements](cpcn-loop-requirements.md)
- [Permissions](cpcn-loop-permission.md)
- [Admin toggles](cpcn-admin-configuration.md)
- [Managing SharePoint Embedded containers](cpcn-loop-spe-management.md)
- [Overview of Loop components in Microsoft 365](loop-components-teams.md)