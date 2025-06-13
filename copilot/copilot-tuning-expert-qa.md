
---

title: Get started with Copilot Tuning models
description: Copilot Tuning models are designed to provide complex, domain-specific answers for user queries within your organization. These models require structured domain content and integrate with Copilot agents for interactive query processing. Explore best practices, scenarios, limitations, and requirements for effective implementation.
manager: [placeholder-metadata]
ms.reviewer: [placeholder-metadata]
ms.topic: get-started
ms.localizationpriority: [placeholder-metadata]
ms.collection: [placeholder-metadata]
ms.custom: [placeholder-metadata]
search.appverid: [placeholder-metadata]
---

# Get started with Copilot Tuning models

> [!INCLUDE metadata-learn-get-started-article-pattern]

Copilot Tuning models are designed to provide complex, domain-specific answers for user queries within your organization. These models require structured domain content and integrate with Copilot agents for interactive query processing. Explore best practices, scenarios, limitations, and requirements for effective implementation.

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

Before starting, ensure the following:

1. You must have domain-specific content or documentation, such as legal playbooks, HR guidelines, technical documentation, policy manuals, or departmental procedures, that the model can use to answer questions.
2. Configure the model agent with an Azure Active Directory (AAD) security group or distribution list and create your own AAD groups to be added to the model.
3. Identify where your content is stored in SharePoint.

:::image type="content" source="placeholder-media" alt-text="Illustration of prerequisites needed for a fine-tuned model":::

## Set up

Set up an **Expert Q&A model** using Copilot tuning model maker. This guide covers creation, configuration, training, and integration.

### Model maker workflow

Model Maker serves as the entry point for selecting the content collection, with Copilot Studio verifying access control by comparing permissions on the content with those of the fine-tuned model.

Model Maker also prompts you to fill out a questionnaire that describes the content and purpose of the Tenant Copilot Declarative Agent. Tenant Copilot uses this information to guide the training data generation, filtering, and behavior adjustment of the Declarative Agent.

To set up an Expert Q&A model, follow these steps to ensure a smooth configuration.

1. In Copilot Studio, select **Create a new model**, and provide the model name, task type, and description.
1. Set up expert content by adding domain-specific documentation.
1. Complete the model maker questionnaire, which helps describe the content, domain expertise, and intended functionality of the Tenant Copilot Declarative Agent. This information is used to guide the training data generation and behavior of the model.
1. Configure model details by defining query handling, multi-turn interaction, and citation depth.

Copilot Studio checks the permissions for the selected content to ensure the security group(s) have appropriate access. Any inaccessible content isn't used during the training process.

### Declarative agent maker workflow

To create an advanced Copilot Declarative Agent specialized for answering questions based on domain-specific knowledge, follow these steps.

1. Define and designate the repositories or databases where your structured content is stored, ensuring that it covers all necessary domain-specific material.
1. Integrate necessary security details by linking the model to the appropriate Azure Active Directory groups, ensuring controlled access and security compliance.
1. Provide domain expertise through a configuration questionnaire, detailing typical questions, key answer points, and the preferred response style and tone.
1. Utilize the system’s capability to automatically draft initial Q&A pairs based on your domain content, forming the foundational training dataset for the agent.
1. Fine-tune the model and, once the training data is prepared, publish it and integrate it with the Copilot agent to initiate user interactions.
1. In Copilot Studio, create a new agent by selecting the “Task-specific” option and choosing the appropriate Copilot Tuning model as the knowledge source for your Expert Q&A Agent.
1. Customize the agent's behavior by providing detailed instructions that guide its responses in terms of tone, style, and length, ensuring alignment with the desired scenario and audience.

## Related content

**Placeholder: TO DO** Main content for related resources and articles will be included here.
