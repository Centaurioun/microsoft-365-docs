---  
title: "Microsoft 365 Copilot Search privacy"  
author: kwekuako
ms.author: kwekua  
manager: dansimp
ms.date: 06/05/2025  
ms.topic: overview
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: CopilotSearch
ms.custom: QuickDraft
ms.reviewer: kwekua
audience: admin
ai-usage: ai-assisted
description: Information on privacy controls for Microsoft 365 Copilot Search.
---


# Microsoft 365 Copilot Search privacy and protection

Microsoft 365 Copilot Search is compliant with our existing privacy, security, and compliance commitments to Microsoft 365 commercial customers, including the [General Data Protection Regulation](/compliance/regulatory/gdpr) (GDPR) and [European Union (EU) Data Boundary](/privacy/eudb/eu-data-boundary-learn).

> [!NOTE]
> Microsoft 365 Copilot Search becomes available in a Targeted release beginning late June 2025. It will become generally available as a Standard release in Q3 2025. Learn more about [Standard and Targeted releases]( /microsoft-365/admin/manage/release-options-in-office-365).

Microsoft 365 Copilot Search can access and reason over the data it has permission to see within a user's Microsoft 365 environment. This includes:

- **Microsoft Graph** - Emails, chats, calendar events, files in OneDrive and SharePoint, and meetings.
- **Microsoft 365 apps** - Word, Excel, PowerPoint, Outlook, Teams, OneNote, and Loop.
- **Third-party apps** - Salesforce, ServiceNow, Confluence and more, via Microsoft 365 Copilot connectors.

Copilot Search only returns information that the user already has access to, respecting existing permissions and security boundaries. For guidelines on how to restrict access to information, see [Manage access to files and sites](/microsoftsearch/manage-access-files-sites).

## Restrict content discovery in SharePoint

With Restricted Content Discovery, organizations can limit the ability of end users to search for files in specific SharePoint sites. When you enable Restricted Content Discovery for each site, it prevents the sites from surfacing content in organization-wide search results and Microsoft 365 Copilot answers, unless a user owns or recently interacted with content on those sites. For more information, see [Restrict discovery of SharePoint sites and content](/sharepoint/restricted-content-discovery).

If you're a SharePoint administrator in Microsoft 365, the Restricted SharePoint Search setting helps you maintain a list of SharePoint sites, known as an **allowed list**. With this list, you allow access to these designated sites after checking permissions and applying data governance. The allowed list specifies which SharePoint sites can be included in organization-wide search and Copilot experiences. By default, the Restricted SharePoint Search setting is turned off, and the allowed list is empty.

Restricted SharePoint search allows you to restrict both organization-wide search and Copilot experiences to a curated set of SharePoint sites of your choice. Even if you enable Restricted SharePoint Search, users in your organization are still able to interact with files and content they own or that they have previously accessed in Copilot. For more information, see [Restricted SharePoint Search](/sharepoint/restricted-sharepoint-search).
