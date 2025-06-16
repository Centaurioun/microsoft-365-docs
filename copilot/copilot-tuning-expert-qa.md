---
title: Configure Copilot Tuning for expert Q&A
author: danielabom
ms.author: danielabo
manager: calvind
ms.reviewer: jwolk
ms.date: 06/04/2025
ms.topic: how-to
ms.localizationpriority: medium
description: This article describes how to use Copilot Tuning to build an AI model for expert Q&A.
---

# Configure Copilot Tuning for expert Q&A

Copilot Tuning models are designed to provide complex, domain-specific answers for user queries within your organization. These models require structured domain content and integrate with Copilot agents for interactive query processing. Explore best practices, scenarios, limitations, and requirements for effective implementation.

[!INCLUDE [copilot-tuning-preview](includes/copilot-tuning-preview.md)]

## Capabilities

You can use the model maker to fine-tune a model that can complete the following capabilities:

- Acts as a special-purpose Declarative Agent trained on proprietary tenant knowledge in specialized domains (e.g., telecom, tax, HR, oil and gas) that are not available on the open web.
- Answers complex, domain-specific questions by reasoning across multiple documents and making sense of distributed content (e.g., comparing regulatory implications across regions).
- Delivers context-rich, nuanced answers using a fine-tuned LLM trained to correlate domain-specific content across documents.
- Maintains scenario-appropriate tone, such as using an empathetic tone for HR-related responses.
- Leverages the M365 Copilot Search stack for real-time enrichment, especially for recently added or updated content.
- Preserves security and access controls by using M365 security groups to gate model training and access.

## Limitations

The model supports various document formats, but there are specific limitations to consider when using your content.

- Content must be stored in SharePoint and be in supported formats (.docx, .pdf, .aspx); elements like embedded images or tables are not supported.
- Not intended for general productivity or web-wide knowledge queries; it is limited to tenant-specific content and not suitable for tasks like managing meetings or browsing general internet data.
- Dependent on the snapshot time of training data, newer content must be enriched via Search.
- Response formatting may differ from standard Copilot Declarative Agents due to being on an older platform version (FluxV2 vs FluxV3), though migration to FluxV3 is in progress.

While there's no minimum document count, better results are achieved with larger content sets; at least 20 documents are recommended for training.

## Prerequisites

Before starting, ensure the following:

1. You must have domain-specific content or documentation, such as legal playbooks, HR guidelines, technical documentation, policy manuals, or departmental procedures, that the model can use to answer questions.
2. Configure the model agent with an Azure Active Directory (AAD) security group or distribution list and create your own AAD groups to be added to the model.
3. Identify where your content is stored in SharePoint.

:::image type="content" source="placeholder-media" alt-text="Illustration of prerequisites needed for a fine-tuned model":::

## Set up

Set up an **Expert Q&A model** using the Copilot tuning model maker. This guide covers creation, configuration, training, and integration.

### Model maker workflow

Model Maker serves as the entry point for selecting the content collection, with Copilot Studio verifying access control by comparing permissions on the content with those of the fine-tuned model.

Model Maker also prompts you to fill out a questionnaire that describes the content and purpose of the Copilot  Tuning declarative agent. Copilot Tuning uses this information to guide the training data generation, filtering, and behavior adjustment of the declarative agent.

To set up an Expert Q&A model, follow these steps to ensure a smooth configuration.

1. In Copilot Studio, select **Create a new model**, and provide the model name and description.
1. Set up expert content by adding domain-specific documentation.
1. Complete the model maker questionnaire, which helps describe the content, domain expertise, and intended functionality of the Copilot Tuning declarative agent. This information is used to guide the training data generation and behavior of the model.
1. Configure model details by defining query handling, multi-turn interaction, and citation depth.

Copilot Studio checks the permissions for the selected content to ensure the security group(s) have appropriate access. Any inaccessible content isn't used during the training process.

### Declarative agent maker workflow

To create an advanced Copilot Declarative Agent specialized for answering questions based on domain-specific knowledge, follow these steps.

1. Define and designate the repositories or databases where your structured content is stored, ensuring that it covers all necessary domain-specific material.
1. Integrate necessary security details by linking the model to the appropriate Azure Active Directory groups, ensuring controlled access and security compliance.
1. Provide domain expertise through a configuration questionnaire, detailing typical questions, key answer points, and the preferred response style and tone.
1. Utilize the system's capability to automatically draft initial Q&A pairs based on your domain content, forming the foundational training dataset for the agent.
1. Fine-tune the model and, once the training data is prepared, publish it and integrate it with the Copilot agent to initiate user interactions.
1. In Copilot Studio, create a new agent by selecting the "Task-specific" option and choosing the appropriate Copilot Tuning model as the knowledge source for your Expert Q&A Agent.
1. Customize the agent's behavior by providing detailed instructions that guide its responses in terms of tone, style, and length, ensuring alignment with the desired scenario and audience.

## Related content

- [Microsoft 365 Copilot Tuning overview (preview)](copilot-tuning-overview.md)
