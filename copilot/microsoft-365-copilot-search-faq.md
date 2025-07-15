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

