---
title: Configure Copilot Tuning for Document Generation
author: jasonjoh
ms.author: jasonjoh
manager: calvind
ms.audience: ITPro
ms.reviewer: jwolk
ms.date: 06/04/2025
ms.topic: how-to
ms.localizationpriority: medium
description: This article describes how to build an AI model for document generation on organizational knowledge through Copilot Studio.
---

# Configure Copilot Tuning for Document Generation

Initial drafts of new documents can be automatically generated using a custom model trained through the Copilot Tuning document generation task. Document generation models leverage a reference document and specified changes to create a draft of a new document.

A model created with the document generation task is particularly valuable when the tone, style, and formatting of existing reference documents must be retained, while generating drafts of new documents based on those reference documents. Document generation is suitable for document creation use-cases such as contracts, compliance, procurement, and other scenarios where a  draft of a document can be based on a reference document such as a sample document or a template document.. It is also applicable for any use case where regular updates to documents are necessary based on change specifications and the previous version of a document.

Use-case fit:

- HR
- Legal
- Compliance
- Procurement
- Documentation

Specific examples include, but are not limited to:

- Recurring contracts
- Sample-based documentation creation
- Documents requiring regular updates to language or content based on change specifications

## Prerequisites

- Must have permission granted in settings to use Copilot Tuning in Copilot Studio.
- Have a collection of reference documents, ( and target documents that are stored in either SharePoint, or on a supported connector.
- Have a collection of change logs or specifications stored on SharePoint or on a supported connector.
- Must provide a structured version of required changes in the supplementary field within Copilot Tuning.

> [!NOTE]
> Document Generation supports working with the following file formats: .doc, .docx, .html, .md, or .pdf.. Currently Copilot Tuning only uses information found text so if there is critical information in images and/or tables in your documents Copilot Tuning document generation will not work well for your task.

## How to configure Copilot Tuning for Document Generation

Document generation offers a solution to efficiently address high volume requests for document creation based on existing reference documents or templates.

This capability is suitable for scenarios where users need to draft new documents that require specific changes starting from an existing original reference document

To start, obtain permission to use the Copilot Tuning interface. [Placeholder: See XXX page about permissions.]

The following are the high-level steps to  configure a custom document generation model using Copilot Tuning:

1. Prepare the a mapping.csv file training data (pairs of reference documents to drafts of new versions of documents, along with the applied specified changes)

2. Customize your model for your task

3. Select security groups

4. Train the Document Generation model

5. Evaluate the model and refine by better labeling or narrowing the training scope

6. Publish the model

The training process begins with inputting original reference documents", specified changes to the original documents and final versions "draft documents" into Copilot Tuning to train the model. During training, Copilot Tuning learns how to apply these changes to generate draft documents.

To create a Document Generation model:

## Prepare you mapping.csv file..

Before using Copilot Studio Copilot Tuning, you need to ensure your data is in a knowledge source Copilot Tuning has access to (i.e. Sharepoint or another supported connector). In your knowledge sources, you should have at least 100 or more example pairs of reference documents, specified changes, and target draft documents. In this step, you will prepare a mapping.csv file that explicitly provides a couple dozen examples of reference documents to final draft documents. Copilot Tuning uses these examples to learn how to find more examples for training from your knowledge source without you having to manually curate them.

1. Ensure training data is available in either ShaSharePoint orwithin a supported connector.
2. Prepare a mapping.csv file and store it in the root directory of your knowledge source. mapping.csv should have two columns.
    1. The first column of mapping.csv should be named "precedent" and should contain the path to the reference documents (see Note above about supported formats) to provide the paths in the data source to the original files.

    1. The second column should be named "target" and should contain the path to the corresponding final draft of the new document.

After you have created a mapping.csv, proceed to customizing your model.

## Customize your model.

1. Obtain permission to access the Copilot Studio Copilot Tuning. This must be granted in the Settings page to unlock the app [placeholder to link to MAC documentation]
2. In Copilot Studio Copilot Studio, click the "Create new" button to start creating a new model.
    1. Specify a name to give your model and provide a description of what the model does Ensure that the model name and description are user-friendly and clearly describe the purpose of the model. This will help users in your organization understand the model's purpose once it is published in a later step.
    1. Choose your knowledge source by clicking "Add knowledge" to select the SharePoint instance or custom connector where training data resides. See Note [placeholder to note above] about supported file types and [placeholder] for more information about knowledge sources.
    1. [Optional] In **Permissions** grant permissions for who can use the model by entering security groups or email addresses of the people in your organization that should be able to use this model. Copilot Tuning will ensure that any knowledge that is not accessible by these selected security groups will be automatically filtered out. [Placeholder: Link to page that describes how security works.] If you don't explicitly give permissions, the model will only be accessible to you.
    1. Set the task type to **Document generation**.
    1. Provide **Model Instructions** about your scenario. Instructions ensure Copilot Tuning is using the terminology your organization uses and evaluates your models output using the criteria one of your users would use to evaluate the document. It is important to accurately answer these questions because this information cues the system how to interpret the underlying data.

Once you are finished providing model instructions, click "Prepare labeling data" to allow Copilot Tuning to prepare your data for training and learn how to find additional examples with which to train your model. Based on your dataset size this step may take up to 24 hours. When it is complete, you will receive an email letting you know that Copilot Tuning is ready for you to go to the next step in the model creation process. In the meanwhile, you can check the status of the model from the Copilot Tuning landing page.

## Review Security Groups and Knowledge Selection after Copilot Tuning ACL Analysis.

Copilot Tuning analyzes the document ACLs of the training corpus you selected and then filters out any knowledge that is not accessible to the security groups selected in the previous step. Please refer to the [placeholder link to ACL documentation page] for more information about ACL analysis and how to select appropriate security groups for your task.

Based on your dataset size this step may take up to 24 hours. When it is complete, you will receive an email letting you know that Copilot Tuning is ready for you to go to the next step in the model creation process. In the meanwhile, you can check the status of the model from the Copilot Tuning landing page.

## Prepare Labeling Data during Automatic Data Preparation.

Starting by learning from the example pairs you provided in mapping.csv, Copilot Tuning starts to learn how to select more samples to finetune with. This is an iterative process whereby at certain points Copilot Tuning may ask you to label data to ensure that the system is doing a good job of identifying more pairs to use to create your finetuned model. When you receive an email letting you know that data is ready for labeling, use the following steps to label the data.

1. Go to the Copilot Studio landing page. Click on a model that has a status indicating that the task has data ready for labeling to bring up the labeling form.

1. The labeling form provides a few sample documents that Copilot Tuning thinks are high quality documents to use as example final draft documents. In this form, examine each document and label whether or not you think the document is a high quality final draft document that this system should use to tune your model.  Once you have determined which documents are good examples of final documents, submit the labeling form.

At this point, you can return to the Copilot Tuning landing page and see the status of your model configuration. Your model configuration may ask you to label more data, may be further processing the data in your knowledge source, or may be ready to finetune the model.

## Train and Evaluate the Document Generation model:

10. Once sufficient data has been prepared by the system, you can proceed with training the model. At this point, finetuning of your model will begin in Azure AI Foundry.

12. O Once the model has been finetuned, Copilot Tuning will generates results that the user can review to evaluate if the model is of sufficient quality to deploy.

15. If the model does not meet your quality bar, you can go to the previous steps in the flow to add more data sources, adjusting the model instructions, or providing more samples in your mapping.csv.

16. Re-train model until document generation results meet expectations.

17. Evaluate the model and ensure compliance with legal standards, style tones, tone context.

## Publish the model:

Once the model meets your quality standards, you can publish the model through the Copilot Tuning interface. Deploy model by selecting Publish Model button. Once the model is published it gets deployed to an isolated and secured catalog that is only accessible to the security groups that were selected during the previous steps.

## Related Content

Once a model is configured for document generation, deploy an Agent to streamline document generation workflows.

For more information, see [How to deploy document generation Copilot capabilities](placeholder-url).

If the document generation model doesn't work, refine the model by re-training using further documents or narrow the focus of training scope.

For more information, see [Toubleshooting: Doc Gen Models](placeholder-md-file).
