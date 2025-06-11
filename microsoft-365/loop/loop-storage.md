---
title: Overview of Loop storage
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
description: Learn about Loop storage in the Microsoft 365 ecosystem.
f1.keywords:
- CSH
ms.custom: 
- NewAdminCenter_Update
- chat-teams-channels-revamp
appliesto: 
- Microsoft Teams
---

# Overview of Loop storage

## Storage

Loop content is stored in SharePoint, OneDrive, and [SharePoint Embedded](/sharepoint/dev/embedded/concepts/admin-exp/consuming-tenant-admin/cta), allowing familiar management within existing file management workflows. Where the content was originally created determines its storage location:

|Content content originally created in|Content stored in SharePoint Embedded|Content stored in SharePoint Site|Content stored in User's OneDrive|Lifetime Management|
|-----|-----|-----|-----|-----|
|Loop app, My workspace|✔️in user-owned container|||user account|
|Loop app, shared workspace|✔️in shared container|||workspace owners|
|Teams [channel workspace](https://techcommunity.microsoft.com/blog/microsoft365insiderblog/collaborate-in-real-time-with-workspaces-in-teams/4414334)|✔️in shared container|||M365 Group|
|Teams channel meeting||✔️in 📁`Meetings`||M365 Group|
|Teams channel||✔️in Channel folder||M365 Group|
|Teams private chat|||✔️in 📁`Microsoft Teams Chat files`|user account|
|Teams private meeting|||✔️in 📁`Meetings`|user account|
|OneNote for Windows or for the web|||✔️in 📁`OneNote Loop files`|user account|
|Whiteboard|||✔️in 📁`Whiteboard\Components`|user account|

## My workspace container name

Copilot Pages and Copilot Notebooks share the Loop My workspace container. This user-owned container appears as 'Pages' if the person first visits the M365 Copilot app, or as 'My workspace' if they first visit the Loop app. To list all user-owned containers in your organization, regardless of their name, use, and adapt the following sample PowerShell:

```PowerShell
Get-SPOContainer -OwningApplicationId 'a187e399-0c36-4b98-8f04-1edc167a0996' | WHERE OwnershipType -EQ 'UserOwned' | FT
```

## Storage quota

All Loop workspaces count against your tenant's SharePoint storage quota.

SharePoint Embedded also offers a platform for developers to build their own applications. This alternate usage pattern which bills per use is different from Loop and Copilot Pages storage quota management.

## Storage limits

Loop workspaces have a maximum size of 25 TB. This limit can't be increased or decreased. Learn more about [SharePoint Embedded container limits](/sharepoint/dev/embedded/concepts/app-concepts/limits-calling).

## Storage management after user departure

### Types of Loop workspaces

There's one personal workspace per user in your organization, created on demand by the person when accessed. All other created Loop workspaces are shared. For more information, see [workspace membership and Microsoft 365 groups](/microsoft-365/loop/cpcn-loop-permission#workspace-membership-and-microsoft-365-groups) on the two shared workspace types.

### Shared Workspaces

#### Tenant-owned

- A roster permissions tenant-owned shared Loop workspaces. If all owners leave the company, the workspace becomes ownerless, remains in the tenant, and isn't automatically deleted.
- You must be an owner to delete a workspace. If all the owners left the company, members can't delete the workspace until an IT administrator adds new owners.

#### Microsoft 365 Group-owned

- The Microsoft 365 group permissions and manages the lifetime of group-owned shared Loop workspaces, similar to the management of SharePoint Team sites.

### Personal Workspaces

- Copilot Pages, Copilot Notebooks, and [My workspace](#my-workspace) store content within the same user-owned SharePoint Embedded container.
- This personal content is private by default, allowing users to work without forced sharing or coauthoring, similar to OneDrive.

#### My workspace

- My workspace is stored in a user-owned SharePoint Embedded container, created by Loop. The container is lifecycle managed with the user account, deleted when the user account is deleted from the organization.
- My workspace can't be permanently reassigned to a new owner. It follows the same cleanup schedule as OneDrive: 30 days active, then soft deleted, and permanently purged 93 days after soft deletion.
- Admins can recover content during the soft delete period using the SharePoint Admin Center or PowerShell.

> [!NOTE]
> A feature for IT admins to assign temporary custodians during the cleanup period of user-owned workspaces isn't yet available. This capability for Copilot Pages, Copilot Notebooks, and My workspace is planned (Microsoft Roadmap ID 421612).

#### Ideas

- The Ideas workspace is deprecated, no longer created by default, and replaced with the My workspace personal workspace.
- Ideas were the first default workspace, was tenant-owned, permissioned with a single-person roster.
- The Loop app doesn't delete the deprecated Ideas workspace; a user or an admin must delete it if needed.
- If a user hasn't added multiple owners to their Ideas workspace, the workspace becomes ownerless when they leave the company. It remains in the tenant and isn't automatically deleted.

### Loop components created in Microsoft 365 outside of the Loop app or Copilot Pages

See [Storage](#storage). When content is stored in OneDrive, if that user leaves the organization, the standard OneDrive IT policy is applied. When content is stored in SharePoint, the standard SharePoint IT policy is applied. Learn more about [OneDrive and SharePoint Retention and Deletion](/sharepoint/retention-and-deletion).

## Related topics

- [Summary of Compliance, Lifecycle, Governance](/microsoft-365/loop/loop-compliance-summary)
- [Requirements](/microsoft-365/loop/cpcn-loop-requirements)
- [Permissions](/microsoft-365/loop/cpcn-loop-permission)
- [Admin toggles](/microsoft-365/loop/loop-admin-configuration)
- [Managing SharePoint Embedded containers](/microsoft-365/loop/cpcn-loop-spe-management)
- [Overview of Loop components in Microsoft 365](/microsoft-365/loop/loop-components-teams)
