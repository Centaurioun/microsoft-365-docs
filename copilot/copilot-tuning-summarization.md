---

hideNav: true
---

# Get started with Tenant Copilot Summarization

Tenant Copilot Summarization generates structured, high-quality summaries from complex documents, aligning summaries with your organization's communication style. The summary generation is available where automation is needed for rephrasing complex text while maintaining organizational tone and style in the following:

- Automated executive reports.
- Contract abstracts.
- Regulatory and internal documentation.

It is ideal when an organization has a high volume of documents that require consistent summaries in a particular style.

Tenant Copilot Summarization is an enterprise solution that offers customization to your enterprise through fine tuning. It ensures and maintains a consistent communication style for your organization, aligned to text-based document and summary pairs provided as training input. It operates in a tenant-specific, isolated environment within Microsoft 365, preserving and maintaining privacy commitments for your business. Within your Microsoft 365 ecosystem, it ensures that user data remains isolated within each tenant, safeguarding the tenant from access by other entities.

## Key capabilities

Tenant Copilot Summarization creates structured summaries with the following capabilities:

- Extraction and rephrasing of key information learned from training examples.
- Maintenance of original document structure and prioritization of key information.
- Summarization in the organizational voice and alignment of text on style.

At the heart of Tenant Copilot is a customized large language model (LLM) tailored to your organization using advanced prompt and modeling techniques. This model goes beyond customization to personalization ensuring efficient and accurate generation summaries, which are consistent with the organization's voice, tone, and style.

Tenant Copilot employs cutting-edge training approaches like few-shot, fine-tuning, and retrieval-augmented generation (RAG) for enhanced agility and precision. These models provide distinct benefits such as improved productivity, consistency across outputs, and seamless integration with Microsoft 365, while mitigating risks associated with domain-specific terminology and confidential data.

Tenant Copilot Summarization combines practicality with sophistication, offering a powerful solution for generating customized summaries, enhancing productivity, and being tailor made for your enterprise applications.

The following diagram illustrates the overall process for generating summaries:

:::image type="content" source="media/copilot-tenant-summarization-solution-overview.png" alt-text="Architecture diagram for Tenant Copilot Summarization solution.":::

The process consists of the following two steps:

- Setup step 1: Training
- Setup step 2: Inference

### Setup step 1: Training

Tenant Copilot Summarization features a straightforward model training process that ensures efficiency and precision in generating high-quality summaries aligned with your organization's voice and style. There are several key steps which are involved throughout the training process:

1. Data extraction: Information is sourced from platforms such as SharePoint. Document and Summary pairs are organized into structured formats ready for supervised training.

    2. Data processing: Parent, document, and target tables are used as data sources within the training library. In this library, a hundred and twenty structured document and summary pairs are organized for a comprehensive training workflow.

3. Fine-tune large language model: Supervised fine-tuning aligns the model with your organization's specific tone and style utilizing the hundred and twenty document and summary pairs. Validation involves checking for preservation of key information and tone, using reserved test data and performance metrics like ROUGE for precision, recall, and F-score.

The training is an efficient process aiming to reduce discrepancies between current predictions and desired outputs based on the training examples. The model is trained on the document and summary pairs using a single pass. The retrieved data is processed using a LLM to create a customized summarization model which aligns closely with the user's existing output style, allowing fast and accurate inference.

When it comes to generating impactful summaries, supervised fine-tuning takes into consideration real-word training samples, allowing it to recognize key sections of a document and produce summaries efficiently and effectively, all while maintaining the organization's specific style as reflected in the training samples. This fine-tuning approach employs an advanced GPT style transformer deployed within Azure's cognitive cluster.

With a consistent focus on rapid turnaround, precision, and adherence to the user's preferred style, the supervised fine-tuning process culminates in models that mirror desired summaries, effectively prioritizing key sections and delivering summaries that align feedback from similar tasks or documents. This results in a customized model tailored for your organization's requirements.

### Setup step 2: Inference

The inference process for Tenant Copilot Summarization is both efficient and consistent, leveraging familiar interfaces to ensure optimal usability. It enables users to submit documents through widely used platforms like Word, SharePoint, or Teams to obtain summaries in familiar environments. When a user provides a source document, the fine-tuned summary model efficiently creates a concise summary in short processing time while maintaining the tone and document structure.

Summary generation is single pass and is prioritized to extract key sections, clauses, and the document's core meaning, reflecting what's deemed most important according to the training examples. Each summarization workflow is executed rapidly supporting output from multiple similar documents in a similar tone, aligned to the training examples. It allows users to focus on value-add activities rather than manually reviewing documents to create summaries from scratch.

Feedback from users plays a pivotal role in maintaining summary quality and allowing for continuous improvement of the model's performance. With its streamlined architecture and user-friendly approach, Tenant Copilot Summarization ensures enterprises can realize consistent summaries from complex documents across a range of existing workflows.

Tenant Copilot Summarization is available within Microsoft 365 apps (like Word, SharePoint, or Teams) via declarative agents in Copilot where documents are submitted to Microsoft 365 Large Language Model in Azure AI. For further details on training and application to your solution, reach out to your account representative.

## Model Training Requirements

The model training process requires input parameters that support text-based document and summary pairs in the following formats:

- .docx
- .pdf (with selectable text)
- .aspx format

These original document and summary pairs are required for training purposes to align the generated summaries to organization communication style.

## End user guidance and support

Tenant Copilot Summarization is tailor made for enterprise integration. It embraces existing user workflows within the applications and supports training process to align document summaries to organizational use-case like meetings or business reports. It addresses operational considerations and offers enhanced flexibility for rapid generation and consistency of summaries.

For further support about the models contact your account representative.
Additional internal guidance and help can be found here: [Microsoft Copilot - AI Assistant](copilot-catalogue.md) document. Fault issues can be raised within existing Microsoft 365 applications guidance and instructions, including links to specific tenant admin site.

## Related content

For solutions architecture references see: [Tenant Copilot](copilot-tenant-overview.md).

For provisioning references see: [Tenant Copilot Provisioning](copilot-tenant-provisioning.md).

FAQs for Tenant Copilot can be found here: [Tenant Copilot FAQ](copilot-tenant-faqs.md).

For further details on deployment on Tenant Copilot, contact your Microsoft representative.

For further details on opportunities on Azure AI deployment, contact your Microsoft Azure representative.
