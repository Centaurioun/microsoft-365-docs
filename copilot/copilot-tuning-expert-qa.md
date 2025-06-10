
---
title: Get started with Tenant Copilot models
description: Tenant Copilot models are designed to provide complex, domain-specific answers for user queries within your organization. These models require structured domain content and integrate with Copilot agents for interactive query processing. Explore best practices, scenarios, limitations, and requirements for effective implementation.
manager: [placeholder-metadata]
ms.reviewer: [placeholder-metadata]
ms.topic: get-started
ms.localizationpriority: [placeholder-metadata]
ms.collection: [placeholder-metadata]
ms.custom: [placeholder-metadata]
search.appverid: [placeholder-metadata]
---


# Get started with Tenant Copilot models

[!INCLUDE [metadata-learn-get-started-article-pattern](placeholder-md-file)]

Test

## Capabilities

You can use Tenant Copilot Studio model maker to fine-tune a model that can complete the following capabilities.

The AI language model is designed to address complex, domain-specific queries that require interpretation, contextual understanding, and multi-turn interaction. For example, Copilot agents powered by the model can accomplish the following:

- **Provide citation-based responses**: This model generates responses that are synthesized from multiple domain-specific content sources such as legal, HR, or technical documentation--where each response is accompanied by citations that validate the accuracy of the information provided.
- **Multi-document reasoning**: This capability is crucial for handling content that is distributed across multiple documents, directories, or folders associated with a common topic of interest, where questions can't be answered from a single source.


## Limitations

The model can work with structured domain content, when the content can be accepted by the following:

- Content file must be in the following file types: .docx, .pdf, .aspx, and other file types listed in this article: [Enterprise Prompting file-type support](placeholder-md-file)
- Content must be stored on a SharePoint repository or any other storage option in this article: [Enterprise Prompting storage support](placeholder-url)
- Content that is scanned or unstructured is not supported.

All language models have certain, inherent technical limitations related to information retrieval, language understanding, reasoning, and problem-solving.


## Prerequisites

Before starting, you should make sure you have the following requirements and content:

1. **Domain-specific content**: You must have the content or documentation related to your specific domain that the model can use to answer questions. For example, legal playbooks, HR guidelines, technical documentation, policy manuals, departmental procedures etc.
2. **Supported file types**: For the various content source types supported, see the latest list of Enterprise Prompting supported [file types](placeholder-md-file).
3. **Model agent security settings**: Models can be integrated with an Azure Active Directory (AAD) [security group or distribution lists](placeholder-url). This configuration is commonly used in the Harmonization of Neural Network (HNN) mechanism [agent solution](nant://placeholders), where a list is automatically created and added to the model. This allows anyone with access to the solution to also be able to utilize the model. To achieve this, you can create your own Azure Active Directory (AAD) groups to be added to the model.
4. **Content storage**: You must know where your content is stored. For example, a SharePoint repository or any other storage options supported within the Enterprise Prompting storage [locations](placeholder-md-file).

When these are completed, continue to learn more about the Getting Started process for the solution.

:::image type="content" source="placeholder-media" alt-text="Illustration of prerequisites needed for a fine-tuned model":::


## Get started

Embark on setting up an Expert Q&A model that provides precise, citation-backed responses using the Tenant Copilot Studio Model Maker. This guide covers creation, configuration, training, and integration, ensuring accurate outputs.

### Model maker workflow

To initiate an Expert Q&A model, follow these steps:

1. **Create a New Model**: In Copilot Studio, select "Create a new model" and provide essential details including the model name, task type, and a brief description of the intended use case.

2. **Set Up Expert Content**: Incorporate domain-specific documentation that the model will rely upon. Ensure this content meets the required file formats and storage specifications for seamless integration.

3. **Configure Model Details**: Input relevant settings that guide how the model handles queries, including the extent of multi-turn interactions and the level of detail in citation-backed responses.

### Declarative agent maker workflow

The following steps outline how to enhance your Expert Q&A model:

1. **Add Knowledge Sources**: Designate the repositories or databases where the structured content is stored, ensuring coverage of all necessary domain-specific material.

2. **Configure Security Parameters**: Integrate necessary security details, linking the model to the appropriate Azure Active Directory (AAD) security groups for controlled access.

3. **Use the Configuration Questionnaire**: Provide domain expertise through a survey detailing typical questions, key points in answers, and preferred response style and tone.

4. **Automatic Q&A Pair Generation**: Utilize the system's capability to automatically draft initial Q&A pairs from your domain content, forming the basis of the training dataset.

5. **Fine-Tune and Deploy the Model**: Once the training data is prepared, engage in the fine-tuning process. Afterward, publish the model, subsequently integrating it with a Copilot agent to commence user interactions.

Through this detailed walkthrough, you ensure the development of an advanced Expert Q&A model that delivers discerning, authoritative responses tailored to your domain.


## Scenarios

Tenants that are looking to fine-tune a model within Copilot Studio are typically looking for an answer capability that is connected with domain-specific content, incorporating key capabilities such as multi-document reasoning, multi-turn dialogue, and contextual citations.

The general workflow to fine-tune a model is the following steps:

- Initiate the model creation
- Add knowledge sources
- Configure security settings
- Use the configuration questionnaire
- Wait for system generation of questions & answers (Q&A) pairs
- Wait for training completion
- Validate success, troubleshoot failure
- Publish the model
- Add copilot agent to agent catalog

The following scenarios can help you get started with setting up a fine-tuned model related to your structured content knowledge base:

### Scenario 1

Create a model fine-tuned to respond accurately to queries related to your key knowledge base.

**Scenario Steps**

1. Initiate Model creation by selecting task type
2. Enter model information, select knowledge bases, configure security settings for model
3. Answer prompt questions to provide domain expertise
4. Wait for generated questions and answers (Q&A)
5. Validate Q&A responses, fine-tune model within prompt based on feedback, Update model with brakes provided including identifying unintelligible answers
6. Publish model
7. Add model to an agent

### Scenario 2

Add copilot agent and deploy agent by categorizing within specific domain or "department" and publishing to catalog for use within organization.

**Scenario Steps**

1. Add agent to specific domain or department
2. Deployer user optic setting
3. Add shared platform within catalog
4. Share and amplify within your organization

**Best practices**

To avoid common mistakes and iterate quickly, consider the following best practices:

- Provide clear, specific guidance on the types of questions the model should answer
- Focus on relevant and structured content to provide effective, accurate results
- Schedule content updates for changes and newly-added information
- Customise the model's response style
- Incorporate important details and useful advice for meeting accuracy requirements
- Involve subject matter experts (SMEs) in the configuration process
- Prepare for iterative improvements and troubleshooting

## Related content

_Main content for related resources and articles will be included here._
