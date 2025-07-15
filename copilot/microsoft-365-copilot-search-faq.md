---  
title: "Microsoft 365 Copilot Search Frequently Asked Questions"  
author: davidedwards
ms.author: davidedwards  
manager: kellis
ms.date: 07/15/2025
ms.topic: overview
ms.service: microsoft-365-admin
ms.localizationpriority: medium
ms.collection: CopilotSearch
ms.custom: QuickDraft
ms.reviewer: davidedwards
audience: admin
ai-usage: ai-assisted
description: A list of Frequently Asked Questions for the Microsoft 365 Copilot search feature.
---

# Frequently Asked Questions about Microsoft 365 Copilot Search

## General

**What is Microsoft 365 Copilot Search?**

Microsoft 365 Copilot Search delivers an AI-powered, unified search experience optimized for work and school. It indexes content across Microsoft 365 apps as well as third-party apps, leveraging the Microsoft Graph to interpret user context, behavioral signals, and organizational relationships. This enables it to return highly personalized, context-aware answers to complex queries.

**What are the differences between Microsoft 365 Copilot Search and Microsoft Search?**

Microsoft 365 Copilot Search is designed as an AI-powered, enterprise-grade search assistant. It understands natural language, context, relationships, and user behavior to deliver personalized, relevant results. It goes beyond keyword matching to interpret intent and provide AI-generated answers with references and follow-up options.

[Microsoft Search](/microsoftsearch/overview-microsoft-search), by contrast, is a more traditional search experience. It relies on keyword-based queries and returns a list of links or documents. While it integrates with Microsoft 365, it lacks the conversational and contextual depth of Copilot Search.

**What are the differences between Microsoft 365 Copilot Search and Copilot Search in Bing?**

Microsoft 365 Copilot Search is an AI-powered universal search experience optimized for work and school. It's available to users with a Microsoft 365 Copilot license and is accessed through the Microsoft 365 app. It helps you quickly find relevant results from your organization, searching across all your Microsoft 365 apps and any third-party apps integrated via Microsoft Graph connectors. It also adheres to the same data protection, privacy standards, and security configurations as Microsoft 365 Copilot. 

[Copilot Search in Bing](https://www.microsoft.com/en-us/bing/copilot-search/), by contrast, is an AI-powered search engine designed for individual users who aren't necessarily using it for work or school. It's accessed through a web browser and doesn't require a Microsoft 365 Copilot license.

**Does Microsoft 365 Copilot Search support natural language queries?**

Yes, Microsoft 365 Copilot Search does support natural language queries.

This means you can type questions or requests in everyday language—like "show me the latest updates from the marketing team” or "find the presentation Rachel shared last week”—and Copilot Search will understand your intent and return relevant results from across Microsoft 365 (emails, files, chats, meetings, and more).

It's designed to go beyond keyword matching by using AI to interpret context, relationships, and meaning, helping you find what you need faster and more intuitively.

**Does Microsoft 365 Copilot Search still support traditional keyword queries?**

Yes, Microsoft 365 Copilot Search also supports traditional keyword queries.

**What languages are supported by Microsoft 365 Copilot Search?**

Copilot Search supports the same languages as Microsoft 365 Copilot generally. See the [list of supported languages](https://support.microsoft.com/en-us/office/supported-languages-for-microsoft-365-copilot-94518d61-644b-4118-9492-617eea4801d8).

**How does Microsoft 365 Copilot Search integrate with Microsoft 365 Copilot?**

Microsoft 365 Copilot Search integrates with Microsoft 365 Copilot, but they're distinct experiences with different scopes and licensing requirements.

Microsoft 365 Copilot Search is deeply integrated into the Microsoft 365 Copilot app as a dedicated Search tab. This integration allows users to:
- Find information across Microsoft 365 and connected third-party systems.
- Seamlessly transition from a search query to a Copilot-generated answer when intent detection suggests a multiturn interaction.
- Expand a Copilot answer and continue the conversation in Copilot Chat, enabling a fluid handoff between search and chat experiences.
 
This design positions Search as the organizing layer for AI, while Chat remains the workspace for task execution. For example, if a user searches for "what is my vacation policy," Copilot Search may surface a summarized answer and offer to continue the conversation in chat for deeper exploration or follow-up actions.

**What types of content can Microsoft 365 Copilot Search access?**

It can search across emails, chats, files, meetings, calendars, and third-party systems integrated via Microsoft Graph connectors.

**Can I use Copilot Search to find information from third-party systems?** 

Yes, Microsoft 365 Copilot Search integrates with third-party systems. This is primarily achieved through [Microsoft 365 Copilot connectors](/microsoft-365-copilot/extensibility/overview-copilot-connector), which allow organizations to bring in data from external platforms like Salesforce, ServiceNow, Confluence, and more. 

Additionally, plugin extensibility enables Copilot to interact with third-party apps during runtime, making it possible to search and act on data across a wide range of systems—all within the Microsoft 365 experience.

**Can I continue a search result in Copilot Chat?**

Yes. Copilot Search allows you to expand results and continue the conversation in chat for deeper exploration or follow-up actions.

**Does Microsoft 365 Copilot Search support bookmark and acronym answers like Microsoft Search?**

Microsoft 365 Copilot Search includes support for admin-curated bookmarks and acronyms, which help surface authoritative, organization-specific answers directly in search results. 

Learn more about [how to create answers](/microsoftsearch/setup-microsoft-search#step-2-create-answers) in Microsoft Search and Copilot Search.

**How is Microsoft 365 Copilot Search different from Microsoft 365 Copilot (Chat)?**

Microsoft 365 Copilot and Microsoft 365 Copilot Search are both AI-powered tools, but they serve different purposes and offer distinct user experiences:

| Feature | Microsoft 365 Copilot Search | Microsoft 365 Copilot (Chat) |
|---|---|---|---|
| **Interaction style** | Query-based (search box) | Conversational (chat-based) |
| **Primary goal** | Retrieve, locate, and recommend content | Generate, summarize, and assist with tasks |
| **Context** | Cross-app, organization-wide | App-specific (e.g., Word, Excel, Outlook) |
| **Data sources** | Microsoft Graph + Third-party connectors | Microsoft Graph + Web + 3P connectors |
| **Best for** | Finding work (e.g., locating files, emails, insights) | Doing work (e.g., drafting, summarizing, automating) |

**In brief**:
- **Copilot Search** helps you find the right information across your organization quickly and intelligently.
- **Copilot (Chat)** helps you get work done by generating content and assisting with tasks in context.

**What are data source filters in Copilot Search?**

The data source filter is in the right rail in of Copilot Search. It enables users to filter the search results, narrowing results to specific data sources in Microsoft 365 or those ingested with connectors, like Outlook, Teams, and Confluence, and Salesforce.

## Licensing and access

**Where can I access Microsoft 365 Copilot Search?**

Microsoft 365 Copilot Search is available through the Microsoft 365 Copilot app. The Microsoft 365 Copilot app is available to users with Entra accounts (work or school) and personal Microsoft accounts. 

The Microsoft 365 Copilot app is available across web, mobile (iOS, Android), and Windows.

**Who can use Microsoft 365 Copilot Search?**

Users with an eligible Microsoft 365 Copilot license see the Copilot Search experience in the Microsoft 365 Copilot app on desktop, web, and mobile. Users who don't have an assigned and eligible Microsoft 365 Copilot license will continue to see the classic search experience in Microsoft 365 (also known as [Microsoft Search](/microsoftsearch/overview-microsoft-search)).

**Is there an additional cost for Microsoft 365 Copilot Search?**

No, there's no additional cost for Microsoft 365 Copilot Search itself. It's included as part of the Microsoft 365 Copilot license.

However, some advanced features that enhance Copilot Search—such as Microsoft Graph connectors—may incur additional costs. These connectors allow organizations to index and search content from third-party systems (like ServiceNow, Salesforce, or Confluence) within the Microsoft 365 ecosystem.

**Microsoft 365 Copilot connectors** are licensed separately and may require Microsoft 365 E5, Microsoft Viva, or additional capacity units depending on the volume and type of data being indexed. Learn more about [Microsoft 365 Copilot connectors](/microsoftsearch/connectors-overview).

Microsoft 365 enterprise customers with eligible licenses (for example, Microsoft 365 E5) are entitled to unlimited index quota for ingesting content through Microsoft 365 Copilot connectors.

**Is Microsoft 365 Copilot Search available with Microsoft 365 Copilot Chat?**

No, Microsoft 365 Copilot Search is not included with Copilot Chat. While both are part of the broader Microsoft Copilot ecosystem, they are licensed and delivered differently.

**Is Microsoft 365 Copilot Search available in SharePoint or other Microsoft 365 apps?**

Microsoft 365 Copilot Search is limited to the Microsoft 365 Copilot app.

## Connectors

**What are Microsoft 365 Copilot connectors?**

Microsoft 365 Copilot connectors increase the discoverability and engagement of your enterprise data by deeply integrating your data into the Microsoft 365 Copilot experience, including Microsoft 365 Copilot Search. With over 100 Copilot connectors available, organizations can ingest and unify data from platforms like Salesforce, ServiceNow, Confluence, Jira, GitHub, and Google Drive into Microsoft Graph. Connectors give Copilot the ability to find, access, and summarize your diverse datasets from different sources, enabling more comprehensive insights.

See this overview of [Microsoft 365 Copilot connectors](/microsoft-365-copilot/extensibility/overview-copilot-connector).

**How do I set up a Microsoft 365 Copilot connector?**

There are three main steps to set up a Copilot connector:
1.	Create a connection.
2.	Register your schema.
3.	Ingest your content to the Microsoft Graph. Each item is sent with properties that match the schema you registered to power your content as discoverable in the Microsoft 365 App. For more information, see [Set up Microsoft 365 Copilot connectors in the Microsoft 365 admin center](/microsoftsearch/configure-connector).

**What are Copilot-offered connectors?**

Copilot-offered connectors are prebuilt connectors provided by Microsoft that allow you to integrate various third-party content sources into Microsoft 365. These connectors help you bring external data into Microsoft 365, making it searchable and accessible within your organization. Learn more about the [Copilot connectors gallery](/microsoftsearch/connectors-gallery).

**Can I build custom connectors?**

Microsoft 365 Copilot custom connectors allow you to integrate your own data sources into Microsoft Graph, enabling you to bring external data into Microsoft 365 experiences. It helps in making your data searchable and accessible within your organization. 

To get started building your first custom connector, see [these instructions](/microsoft-365-copilot/extensibility/build-your-first-connector?context=graph%2Fcontext). For more detailed instructions about building a custom connector using graph APIs, see these guidelines on working with the [Copilot connectors API](/graph/connecting-external-content-connectors-api-overview).

## Data handling, privacy, and security

**Does Microsoft 365 Copilot Search follow the same data, privacy, and security commitments as Microsoft 365 Copilot?**

Microsoft 365 Copilot Search is compliant with our existing privacy, security, and compliance commitments to Microsoft 365 commercial customers, including the General Data Protection Regulation (GDPR) and European Union (EU) Data Boundary.

For additional information refer to [Data, Privacy, and Security for Microsoft 365 Copilot](/copilot/microsoft-365/microsoft-365-copilot-privacy).

**What information does Microsoft 365 Copilot Search have access to?**

Microsoft 365 Copilot accesses and reasons over the data you already have permission to see within your Microsoft 365 environment. This includes:

| Data source | Examples |
|---|---|---|---|
| **Microsoft Graph** | Emails, chats, calendar events, files in OneDrive and SharePoint, meetings |
| **Microsoft 365 apps** | Word, Excel, PowerPoint, Outlook, Teams, OneNote, Loop |
| **Third-party systems** (optional) | Salesforce, ServiceNow, Confluence, etc. via [Microsoft 365 Copilot connectors](/microsoft-365-copilot/extensibility/overview-copilot-connector) |
| **Web content** | N/A | 

Copilot only returns information that the user already has access to—respecting existing permissions and security boundaries.

**How can I manage what information Microsoft 365 Copilot Search can find?**

With Restricted Content Discovery, organizations can limit the ability of end users to search for files from specific SharePoint sites. Enabling Restricted Content Discovery for each site prevents the sites from surfacing in organization-wide search and Microsoft 365 Copilot Business Chat, unless a user had a recent interaction.

Learn more at [Restrict discovery of SharePoint sites and content](/sharepoint/restricted-content-discovery).

In addition, Restricted SharePoint Search is a setting that helps you as a [SharePoint Administrator](/sharepoint/sharepoint-admin-role) or [above](/microsoft-365/admin/add-users/about-admin-roles) in Microsoft 365 to maintain a list of SharePoint sites ("allowed list") that you have checked the permissions and applied data governance for. The allowed list defines which SharePoint sites can participate in organization-wide search and Copilot experiences. By default, the Restricted SharePoint Search setting is turned off and the allowed list is empty.

Restricted SharePoint Search allows you to restrict both organization-wide search and Copilot experiences to a curated set of SharePoint sites of your choice. Additionally, whether you have enabled Restricted SharePoint Search, users in your organization are still able to interact with files and content they own or that they have previously accessed in Copilot.

Learn more at [Restricted SharePoint Search](/sharepoint/restricted-sharepoint-search).

## Miscellaneous

**What is the Microsoft 365 Copilot extension and how does it work with Microsoft 365 Copilot Search?**

The Microsoft 365 Copilot extension is a cross-browser add-on that enhances your Microsoft 365 Copilot search results. This extension brings together information from tickets, files, documents, and tasks across multiple work-related third-party sites, providing you with highly relevant and personalized search results.

**How does the Microsoft 365 Copilot extension work?**

The Microsoft 365 Copilot extension works in the background without any manual steps after installation. It is enabled by your organization through the Microsoft Edge Add-Ons website or the Chrome Web store (extensions). The extension only uses activity from third-party apps or sites configured by your organization and does not track your general web browsing. Data captured is stored securely and used only to improve your own Copilot Search experience. It is not shared with others. 

Learn more about the [Microsoft 365 Copilot extension](/microsoftsearch/crossover-browser).