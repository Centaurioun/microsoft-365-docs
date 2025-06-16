---
title:  Configure Copilot Tuning for Expert Q&A
author: danielabom
ms.author: danielabo
manager: calvind
ms.reviewer: jwolk
ms.date: 06/17/2025
ms.topic: how-to
ms.localizationpriority: medium
description: Learn how to use Copilot Tuning to build an AI model for expert Q&A.
---

# Configure Copilot Tuning for expert Q&A

Copilot Tuning models are designed to provide complex, domain-specific answers for user queries within your organization. These models require structured domain content and integrate with Copilot agents for interactive query processing. Explore best practices, scenarios, limitations, and requirements for effective implementation.

[!INCLUDE [copilot-tuning-preview](includes/copilot-tuning-preview.md)]

## Capabilities

You can use the model maker to fine-tune a model that can complete the following capabilities:

- Provide significant value when evaluating content collections that involve specialized and proprietary tenant knowledge, such as internal legal contracts, HR policies, and industry-specific data (e.g., oil and gas), which are not easily accessible online.
- Handle multi-document reasoning to manage content distributed across multiple documents, directories, or folders associated with a common topic of interest, where questions can't be answered from a single source.

## Limitations

The model supports various document formats, but there are specific limitations to consider when using your content.

- Supported file types: `.docx`, `.pdf`, and `.aspx`.
- Content must be stored in SharePoint.
- Certain types of content are not supported, including embedded images or tables.

While there is no lower limit to the number of documents that can be used, you can experience better results with a larger document base and it is recommended that you have at least 20 documents before training.

## Prerequisites

Before you start, make sure that you have the following prerequisites in place:

1. You must have domain-specific content or documentation, such as legal playbooks, HR guidelines, technical documentation, policy manuals, or departmental procedures, that the model can use to answer questions.
2. Configure the model agent with a Microsoft Entra ID security group or distribution list and create your own Entra ID groups to be added to the model.
3. Identify where your content is stored in SharePoint.

## Set up an expert Q&A model

Set up an **Expert Q&A model** using Copilot Tuning model maker in Microsoft Copilot Studio. 

### Model maker workflow

To set up an Expert Q&A model:

1. In Copilot Studio, select **Create a new model**, and provide the model name, task type, and description.
1. Set up expert content by adding domain-specific documentation.
1. Complete the fields to describe the content, domain expertise, and intended functionality of the Copilot Tuning declarative agent. This information is used to guide the training data generation and behavior of the model.
1. Configure model details by defining query handling, multi-turn interaction, and citation depth.

Copilot Studio checks the permissions for the selected content to ensure the security group or groups have appropriate access. Any inaccessible content isn't used during the training process.

### Declarative agent maker workflow

To create a declarative agent for Microsoft 365 Copilot that answers questions based on domain-specific knowledge:

1. Define and designate the repositories or databases where your structured content is stored and ensure that it covers all necessary domain-specific material.
1. Integrate necessary security details by linking the model to the appropriate Entra ID groups, ensuring controlled access and security compliance.
1. Provide domain expertise through a configuration questionnaire, including typical questions, key answer points, and the preferred response style and tone.
1. Use the system's capability to automatically draft initial Q&A pairs based on your domain content, forming the foundational training dataset for the agent.
1. Fine-tune the model and, when the training data is prepared, publish it and integrate it with the agent to initiate user interactions.
1. In Copilot Studio, create a new agent by selecting the "Task-specific" option and choosing the appropriate Copilot Tuning model as the knowledge source for your Expert Q&A agent.
1. Customize the agent's behavior by providing detailed instructions that guide its responses in terms of tone, style, and length to ensure that is aligns with your scenario and audience.

## Related content

- [Microsoft 365 Copilot Tuning overview (preview)](copilot-tuning-overview.md)
