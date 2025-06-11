---
ms.date: 06/10/2025
title: "Manage Copilot Pages, Copilot Notebooks, and Loop components in your organization"
ms.reviewer: dancost, tonchan
ms.author: jenz
author: jenzamora
manager: jtremper
recommendations: true
audience: Admin
f1.keywords:
- NOCSH
ms.service: loop
ms.localizationpriority: medium
ms.topic: how-to
ms.collection:
- Strat_SP_admin
- Microsoft 365-collaboration
- Tier3
- essentials-manage
- magic-ai-copilot
search.appverid:
- SPO160
- MET150
description: "Manage Copilot Pages, Copilot Notebooks, and Loop in your organization"
---

# Requirements for Copilot Pages, Copilot Notebooks, Loop components, and Loop workspaces

Copilot Pages and Copilot Notebooks and their integrations are backed by `.loop` files, stored in user-owned SharePoint Embedded containers. Learn more about [storage and lifecycle](/microsoft-365/loop/cpcn-storage), which is quota combined with SharePoint in your tenant. IT admins can [manage creation of Copilot Pages and Copilot Notebooks](/microsoft-365/loop/cpcn-admin-configuration) using Cloud Policy.

Loop components and integrations are backed by `.loop` files (earlier releases of Loop created these as `.fluid` files), stored in OneDrive, SharePoint, or SharePoint Embedded. Learn more about [storage](/microsoft-365/loop/loop-storage), which is quota combined with SharePoint in your tenant. IT admins can manage creation of Loop components and Loop workspaces by following instructions in this [admin configuration](/microsoft-365/loop/loop-admin-configuration) article.

## URLs and IP address ranges

Just like other Microsoft 365 experiences, Copilot Pages, Copilot Notebooks, and Loop also leverage core services across SharePoint and Microsoft 365. To effectively enable creation of Copilot Pages, Copilot Notebooks, Loop content and Loop integration experiences, follow the instructions in the [Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges) to ensure connections to Loop services (also used by Copilot Pages and Copilot Notebooks) are available and enabled.

## WebSocket connections

Copilot Pages, Copilot Notebooks, and Loop's near real-time communications are enabled by the core services that run a WebSocket server. Coauthors in the same session need to establish secure WebSocket connections to this service to send and receive collaborative data such as changes made by others, live cursors, presence, and so on. Allow list WebSocket traffic to the `*.svc.ms` and `*.office.com` endpoints.

## License requirements

### Copilot Pages and Copilot Notebooks

Copilot Pages are available to anyone in Entra ID accounts with a OneDrive license. Copilot pages require a OneDrive site to function. However, if a OneDrive site exists and the license is later removed, Copilot pages continue to work.

Copilot Notebooks require the [Microsoft 365 Copilot license](/copilot/microsoft-365/microsoft-365-copilot-licensing).

### Loop

Loop components are available to anyone in Entra ID accounts with a OneDrive or SharePoint license.

Licensing through the Loop with workspaces service plan covers the creation of new workspaces and management of workspace members. The full set of experiences enabled and the specific licenses that include the Loop with workspaces service plan are covered in [Loop access via Microsoft 365 subscriptions](https://support.microsoft.com/office/loop-access-via-microsoft-365-subscriptions-92915461-4b14-49a4-9cd4-d1c259292afa). 

## Exchange Online mailboxes

To utilize all features, including at mentions and Loop workspace sharing, it's necessary for all users to have an Exchange Online mailbox. Those with Exchange On-Premises mailboxes will not have access to the full range of capabilities.

## Related topics

- [Copilot Pages and Notebooks, Summary of Compliance, Lifecycle, Governance](/microsoft-365/loop/cpcn-compliance-summary)
- [Copilot Pages and Notebooks Storage](/microsoft-365/loop/cpcn-storage)
- [Permissions](/microsoft-365/loop/cpcn-loop-permission)
- [Copilot Pages and Notebooks Admin toggles](/microsoft-365/loop/cpcn-admin-configuration)
- [Managing SharePoint Embedded containers](/microsoft-365/loop/cpcn-loop-spe-management)
- [Loop Summary of Compliance, Lifecycle, Governance](/microsoft-365/loop/cpcn-compliance-summary)
- [Loop Storage](/microsoft-365/loop/cpcn-storage)
- [Loop Admin toggles](/microsoft-365/loop/loop-admin-configuration)
- [Loop access via Microsoft 365 subscriptions](https://support.microsoft.com/office/loop-access-via-microsoft-365-subscriptions-92915461-4b14-49a4-9cd4-d1c259292afa)
- [Overview of Loop components in Microsoft 365](/microsoft-365/loop/loop-components-teams)
- [Use Loop components in Outlook](https://support.microsoft.com/office/9b47c279-011d-4042-bd7f-8bbfca0cb136)
- [Use Loop components in OneNote](https://support.microsoft.com/office/use-loop-components-in-onenote-ed8a43d9-f6fd-4ad6-bc9d-8841db4da459)
- [Loop components in Whiteboard](https://support.microsoft.com/office/loop-components-in-whiteboard-c5f08f54-995e-473e-be6e-7f92555da347)
- [Get started with Microsoft Loop - Microsoft Support](https://support.microsoft.com/office/get-started-with-microsoft-loop-9f4d8d4f-dfc6-4518-9ef6-069408c21f0c)
