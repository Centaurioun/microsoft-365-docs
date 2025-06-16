---

hideNav: true
---

# Get started with Tenant Copilot Summarization

Tenant Copilot Summarization generates high-quality summaries from complex documents presented in your organization's communication style.  Summary generation  rephrases complex documents and can generate consistent outputs like:

- Automated executive reports.
- Business contract abstracts.
- Regulatory and internal documentation.

It is ideal when an organization has a high volume of documents that require consistent summaries in a particular style.

You customize Tenant Copilot Summarization for your enterprise through fine tuning. This maintains a consistent communication style for your organization, using text-based documents and summary pairs provided as training input. It operates in a tenant-specific, isolated environment within Microsoft 365, respecting th privacy commitments for your business. Working in your Microsoft 365 ecosystem, user data remains isolated within your tenant, safeguarding access by other entities.

[!INCLUDE [copilot-tuning-preview](includes/copilot-tuning-preview.md)]

## Key capabilities

Tenant Copilot Summarization creates structured summaries with the following properties:

- Extraction and rephrasing of key information based on training examples.
- Maintenance of the original document structure that prioritizes key information.
- Summarizes in the organizational voice and style.

At the heart of Tenant Copilot is a customized large language model (LLM) tailored to your organization using advanced prompt and modeling techniques. This model ensures efficient and accurate generation summaries, consistent with the organization's voice, tone, and style.

Tenant Copilot employs training approaches like few-shot, fine-tuning, and retrieval-augmented generation (RAG) for enhanced agility and precision. These models improve productivity, ensure consistency across outputs, and integration with Microsoft 365, while mitigating risks associated with domain-specific terminology and confidential data.

The following diagram illustrates the overall process for generating summaries:

:::image type="content" source="media/copilot-tenant-summarization-solution-overview.png" alt-text="Architecture diagram for Tenant Copilot Summarization solution.":::

## Model training requirements

The model training process requires input parameters that support text-based document and summary pairs in the following formats:

- .docx
- .pdf (with selectable text)
- .aspx format

These original document and summary pairs are required for training purposes to align the generated summaries to organization communication style.

## Model training setup

Tenant Copilot Summarization has a straightforward model training process:

1. Data extraction: Information is sourced from platforms such as SharePoint. Document and Summary pairs are organized into structured formats ready for supervised training.

2. Data processing: Parent, document, and target tables are used as data sources for the training library. A hundred and twenty structured document and summary pairs are organized for the training workflow.

3. Fine-tuning: Supervised fine-tuning aligns the model with your organization's specific tone and style using the hundred and twenty document and summary pairs. Validation involves checking for preservation of key information and tone, using reserved test data and performance metrics.

This training aims to reduce discrepancies between current predictions and desired outputs based on the training examples. The model is trained on the document and summary pairs using a single pass. The retrieved data is processed using a LLM to create a customized summarization model which aligns closely with the user's existing output style, allowing fast and accurate inference.

The supervised fine-tuning step considers real-word training samples, allowing it to recognize key sections of a document and produce summaries efficiently and effectively. This fine-tuning approach employs an advanced GPT style transformer deployed in Azure.

## Model inference

The inference for Tenant Copilot Summarization enables users to submit documents through platforms like Word, SharePoint, or Teams to obtain summaries in familiar environments. When a user provides a source document, the fine-tuned model efficiently creates a concise summary in short processing time while maintaining tone and document structure.

Summary generation is single pass and is prioritized to extract key sections, clauses, and the document's core meaning, reflecting what's deemed most important according to the training examples.  These summaries allow users to focus on value-add activities rather than manually reviewing documents to create summaries from scratch.

Feedback from users plays a pivotal role in maintaining summary quality and allowing for continuous improvement of the model's performance.

Tenant Copilot Summarization is available within Microsoft 365 apps (like Word, SharePoint, or Teams) via declarative agents in Copilot where documents are submitted to Microsoft 365 Large Language Model in Azure AI.

## Enterprise integration

Tenant Copilot Summarization embraces existing user workflows within the applications they already use and supports training process to create document summaries specific to organizational use-case like meetings or business reports.

## Next steps

Additional internal guidance and help can be found here: [Microsoft Copilot - AI Assistant](copilot-catalogue.md) document. Fault issues can be raised within existing Microsoft 365 applications guidance and instructions, including links to specific tenant admin site.

## Related content

For solutions architecture references see: [Tenant Copilot](copilot-tenant-overview.md).

For provisioning references see: [Tenant Copilot Provisioning](copilot-tenant-provisioning.md).

FAQs for Tenant Copilot can be found here: [Tenant Copilot FAQ](copilot-tenant-faqs.md).

For further details on deployment on Tenant Copilot, contact your Microsoft representative.

For further details on opportunities on Azure AI deployment, contact your Microsoft Azure representative.
