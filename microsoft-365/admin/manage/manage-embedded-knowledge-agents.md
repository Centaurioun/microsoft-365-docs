---
title: "Manage agents with embedded file content as a knowledge source in the Microsoft 365 admin center"
ms.author: camillepack
author: camillepack
manager: scotv
ms.date: 06/18/2025
audience: Admin
ms.topic: concept-article
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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
description: "Learn how to manage agents with embedded file content as knowledge in the Microsoft 365 admin center, including file uploads, container handling, and sensitivity labels."
---

# Manage agents with embedded file content as a knowledge source in the Microsoft 365 admin center

Agent builders can use [Copilot Studio agent builder](/microsoft-365-copilot/extensibility/copilot-studio-agent-builder-build) to upload files for the agent to use as knowledge. The uploaded files are stored in tenant-owned [SharePoint Embedded](/sharepoint/dev/embedded/overview) containers, and the file content is embedded as knowledge for the agent to use in responses.

This article explains how embedded files are handled, how admins can manage agents and containers, and what to expect when working with sensitivity labels and deletion workflows.

## Supported file types and limits

Embedded knowledge agents support uploading files as knowledge sources. Only the text content of these files is used for grounding.

### Supported file types

- `.doc`, `.docx`  
- `.ppt`, `.pptx`  
- `.xls`, `.xlsx`  
- `.pdf`  
- `.txt`  
- `.csv`

### Maximum file size

- 150 MB for `.doc`, `.ppt`, `.xls`, `.xlsx`, `.txt`, and `.csv`
- 512 MB for `.docx`, `.pptx`, and `.pdf`  

Files that exceed these limits aren't accepted.

### Maximum number of files

You can upload up to **20 files per agent**.

## SharePoint Embedded containers

When a file is uploaded to an agent, it's stored in a SharePoint Embedded container that's provisioned and owned by the tenant. These containers are automatically created and appear in the SharePoint admin center and PowerShell under the application name `Declarative Agent`.

>[!IMPORTANT]
> Don't delete these containers. Doing so might break the functionality of agents that rely on them.

## View agent metadata

On the **Agents & connectors** page in the Microsoft 365 admin center, you can filter the agent inventory to view only agents that use embedded files as knowledge sources.

:::image type="content" source="../../media/knowledge-agent-filter.png" alt-text="Screenshot showing the agents and connectors page in the Microsoft 365 admin center with the filters highlighted." lightbox="../../media/knowledge-agent-filter.png":::

For each agent, the following metadata is available:

- **File name** – The name of the uploaded file.  
- **File sensitivity** – The sensitivity label applied to the file. (Coming in July 2025)
- **SharePoint container ID** – The unique identifier for the container storing the file.  

This metadata helps admins track and audit the use of embedded content across agents.

## Delete agents

You can delete agents directly from the Microsoft 365 admin center. When an agent is deleted, the following actions occur:

1. The agent is removed from the inventory.  
2. All associated files are deleted.  
3. The underlying SharePoint Embedded container is also deleted.  

:::image type="content" source="../../media/knowledge-agent-delete.png" alt-text="Screenshot showing the pop-up window that appears when deleting an agent." lightbox="../../media/knowledge-agent-delete.png":::

This deletion process is **irreversible**. Once an agent is deleted, it might take up to **24 hours** for the deletion to propagate to all users who had access to it. During this time, users might still see the agent listed, but they'll no longer be able to interact with it once the deletion is complete.

>[!NOTE]
>
> - The deletion workflow differs slightly depending on how the agent was created:
> - Agents created using Copilot Studio agent builder or the Microsoft 365 Agents Toolkit can be deleted from the Microsoft 365 admin center.  
> - Agents created from Copilot Studio can be managed and deleted from the Power Platform admin center.

## Sensitivity labels and access control

>[!IMPORTANT]
> This feature is expected to roll out in July 2025.

Sensitivity labels are applied at the agent level based on the labels of the uploaded files. The assignment of the embedded content label is as follows:

- The label applied to the agent is determined by whichever of the following is more restrictive:
  - Most restrictive sensitivity label of all filed uploaded (for example, the highest priority of the labels on the uploaded files).
  - The tenant’s default sensitivity label for document entities, if one is configured.
- If a default sensitivity labeling policy is in place, a label is automatically assigned.  
- Sensitivity labels are only applied if the agent is created using Microsoft Copilot Studio Agent Builder, and if the agent has embedded files in it.

You can view the sensitivity label for each agent in the **Overview** tab of the Microsoft 365 admin center.

:::image type="content" source="../../media/knowledge-agent-idea.png" alt-text="Screenshot showing the overview details of an agent." lightbox="../../media/knowledge-agent-idea.png":::

### User access and visibility

- If a user doesn't have access to any of the sensitivity labels applied to the uploaded files, they won't be able to access the agent.  
- If a user does have access, they're able to view the agent’s sensitivity label in the agent details pane.  
- Starting **May 31, 2025**, sensitivity labels will appear in the agent details pane when users select the agent link.
