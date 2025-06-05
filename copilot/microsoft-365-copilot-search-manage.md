---  
title: "Microsoft 365 Copilot Search"  
author: kwekuako
ms.author: kwekua  
manager: dansimp
ms.date: 06/05/2025  
ms.topic: Overview
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: CopilotSearch
ms.custom: QuickDraft
ms.reviewer: kwekua
audience: admin
ai-usage: ai-assisted
description: Information on how to manage Microsoft 365 Copilot Search.
---

# Manage Microsoft 365 Copilot Search

No action is required by admins to set up Microsoft 365 Copilot Search. If a user has a Microsoft 365 Copilot license, they can access Copilot Search from the **Search** tab in the Microsoft 365 Copilot app. Users who don't have the Microsoft 365 Copilot app will receive the Microsoft Search experience when clicking the **Search** tab in the Microsoft 365 app.

> [!NOTE]
> Microsoft 365 Copilot Search becomes available in a Targeted release beginning late June 2025. It will become generally available as a Standard release in Q3 2025. Learn more about [Standard and Targeted releases]( /microsoft-365/admin/manage/release-options-in-office-365).

## Copilot Search and Third-Party Systems

Copilot Search can access and reason over data in third-party systems as well as Microsoft 365 apps and other systems in the Microsoft Graph. This is achieved through Microsoft 365 Copilot connectors, which allow organizations to bring in data from external platforms like Salesforce, ServiceNow, Confluence, and more. Additionally, plugin extensibility enables Copilot Search to interact with third-party apps during runtime, making it possible to search and act on data across a wide range of systems, all within the Microsoft 365 experience.

[Learn more about Microsoft 365 Copilot connectors](/microsoft-365/copilot/connectors).

## Microsoft 365 Copilot Extension

The Microsoft 365 Copilot Extension is a cross-browser add-on that enhances your Copilot Search results. This extension brings together information from tickets, files, documents, and tasks across multiple work-related third-party sites, providing highly relevant and personalized search results.

The Microsoft 365 Copilot Extension works in the background without any manual steps after installation. It is enabled by your organization through the Microsoft Edge Add-Ons website or the Chrome Web store (extensions). The extension only uses activity from third-party apps or sites configured by your organization and doesn't track your general web browsing. Data captured is stored securely and used only to improve your Copilot Search experience and is not shared with others.

For the preview program, we support the following third-party apps or connectors: ADO, ServiceNow KB, ServiceNow Catalog, ServiceNow Tickets, Jira, Google Drive, Confluence, and GitHub.

[Learn more about the Microsoft 365 Copilot Extension](/microsoftsearch/crossover-browser).

## Bookmarks and Acronyms

As the admin, you can curate bookmarks and acronyms for Copilot Search just as you can for Microsoft Search. Curating bookmarks and acronyms helps surface authoritative, organization-specific answers directly in search results. These features are designed to:

- Promote key resources - [Bookmarks](/microsoftsearch/manage-bookmarks)
- Define internal terminology - [Acronyms](/microsoftsearch/manage-acronyms)
- Improve discoverability and reduce confusion across teams and departments

## Manage Access to Files and Sites

Organizations can restrict end users from searching for files in certain SharePoint sites by enabling Restricted Content Discovery. This setting prevents the sites from appearing in organization-wide search results and Microsoft 365 Copilot answers unless a user owns or has recently interacted with content on those sites.

Learn more about [restricting content discovery in SharePoint](/sharepoint/restricted-content-discovery).

Admins can also manage access to other sensitive organizational data using tools, policies, and techniques tailored to their needs. Microsoft offers solutions to prevent the oversharing of sensitive data and identify sites with the most sensitive documents.

Learn more about [managing access to files and sites](/microsoftsearch/manage-access-files-sites).
