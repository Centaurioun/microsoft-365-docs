---  
title: "Microsoft 365 Copilot Search"  
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
description: An overview of the Microsoft 365 Copilot search feature.
---

# Microsoft 365 Copilot Search

Microsoft 365 Copilot Search is an AI-powered, enterprise-grade search experience optimized for work and school. It provides a familiar search experience that helps users find relevant results from your organization and the web.

Copilot Search indexes content across Microsoft 365 and third-party applications, leveraging the Microsoft Graph to interpret user context, natural language, behavioral signals, and organizational relationships. This gives Copilot Search unique insights into a user's work data, enabling it to return highly personalized answers to a user's queries.

Because it's integrated with Microsoft 365 Copilot, users can find the results they need with search, then seamlessly transition to chat for deeper exploration or follow-up task completion.

> [!NOTE]
> Microsoft 365 Copilot Search becomes available in a Targeted release beginning late June 2025. It will become generally available as a Standard release in Q3 2025. Learn more about [Standard and Targeted releases]( /microsoft-365/admin/manage/release-options-in-office-365).

## Access and eligibility

Copilot Search is available to users with an eligible Microsoft 365 Copilot license at no additional cost. It can be accessed through the Microsoft 365 Copilot app on desktop, web, and mobile platforms. The app is available to users with Entra accounts (work or school) and personal Microsoft accounts.

No action is required by admins or users to set up Copilot Search. If a user has an eligible Microsoft 365 Copilot license, Copilot Search appears as a tab in the Microsoft 365 Copilot app.

Users without an assigned and eligible Microsoft 365 Copilot license will see the classic search experience in Microsoft 365, known as [Microsoft Search](/microsoftsearch/overview-microsoft-search).

Copilot Search isn't included with [Microsoft 365 Copilot Chat](/copilot/overview). While both are part of the broader Microsoft Copilot ecosystem, Copilot Search requires a Microsoft 365 Copilot license, while Copilot Chat does not.

## Differences Between Copilot Search and Microsoft Search

Microsoft 365 Copilot Search is designed as an AI-powered, enterprise-grade search assistant. It’s a universal work-search experience, helping you find the content you need in Microsoft 365 as well as third-party applications. It understands natural language, context, relationships, and user behavior to deliver personalized, relevant results. It goes beyond keyword matching to interpret user intent and provide AI-generated answers with references and options to follow up using Copilot Chat.

[Microsoft Search](/microsoftsearch/overview-microsoft-search), by contrast, is a more traditional search experience. It relies on keyword-based queries and returns a list of links or documents. While it integrates with Microsoft 365, it lacks the conversational and contextual depth of Copilot Search.

## How Copilot Search Works with Microsoft 365 Copilot

Copilot Search is integrated into the Microsoft 365 Copilot app as a dedicated **Search** tab. This integration allows users to:

- Use natural language to find information across Microsoft 365 and connected third-party systems.
- Seamlessly transition from a search query to a Copilot-generated answer when intent detection anticipates a multiturn interaction.
- Expand a Copilot Search answer and continue the conversation in Copilot Chat, enabling a fluid handoff between search and chat experiences.

This design positions search as the organizing layer for AI, while chat remains the workspace for task execution and deeper interactions. For example, if a user searches for **what's the status of the Q2 report**, Copilot Search may return a summarized answer and offer to continue the conversation in chat for more nuanced exploration or follow-up actions.

## Natural Language Search

Copilot Search supports natural language queries, allowing users to type questions or requests in everyday language. For example, you can search for, **show me the latest updates from the marketing team** or **find the presentation Rachel shared last week**, and Copilot Search will understand your intent and return relevant results from across Microsoft 365, including emails, files, chats, meetings, and more.

Copilot Search goes beyond keyword matching by using AI to interpret context, relationships, and meaning, helping you find what you need faster and more intuitively. It also supports traditional keyword queries for specific words or short phrases, relying on exact or partial matches. But a natural language query can engage AI to better interpret the context of the query, leading to more relevant results.

## Answer Types

Depending on the query, Copilot Search can provide concise, authoritative answers that are relevant to your organization. These answers are delivered directly in search results and deliver information about your organization's acronyms, bookmarks, and people.

- **Acronym answers:** Define terminology used in the workplace.
- **Bookmark answers:** Promote key resources in your organization.
- **People Answers:** Surface coworkers' roles and show how they fit into the organization.

For more information, see [how to curate bookmarks and acronyms for Copilot Search](/copilot/microsoft-365/microsoft-365-copilot-search-manage?view=o365-worldwide).
