---
title: Configure Tenant Copilot for Document Generation
author: jasonjoh
ms.author: jasonjoh
manager: calvind
ms.audience: ITPro
ms.reviewer: calvind
ms.date: 06/04/2025
ms.topic: how-to
ms.localizationpriority: medium
description: This article describes how to configure and deploy Tenant Copilot.
---

# Configure Tenant Copilot for Document Generation

Documents can be generated based on existing templates using Tenant Copilot. With this capability, changes to documents can be automated using a custom Copilot model tailored specifically for the document generation use-case.

Document Copilot is particularly valuable when the legal tone, style, and formatting of existing template documents must be retained, while generating new versions based on those templates. Document generation is suitable for high-volume document creation use-cases across legal work (for example, contracts) compliance, procurement, and other scenarios where the precedence, or the final version of the document is based on standardized template documents. It is also applicable for any use-case where regular updates to documents are necessary based on change specifications or logs and template documents.

Use-case fit:

- Legal
- Compliance
- Procurement

Specific examples include, but are not limited to:

- Recurring contracts
- Precedent based documentation creation
- Documents requiring regular updates to language or content based on change specifications

## Prerequisites

- Must have permission granted in settings to use Copilot Studio.
- Have precedent base template documents (text-based .pdf, .docx file formats) and final target documents that are stored in either SharePoint, or on a supported connector.
- Have change logs or specifications stored on SharePoint or on a supported connector.
- Must provide a structured version of required changes in the supplementary field within Tenant Copilot.

> [!NOTE]
> Document Generation supports working with the following file formats: .docx or text-based PDFs. Scanned images or unstructured content in PDFs isn't supported.

## How to configure Tenant Copilot for Document Generation

Document generation offers a solution to efficiently address high volume requests for document creation based on existing template contracts, or updating documents based on change specifications.

This capability is suitable for scenarios where users need new versions of documents that require specific changes made to existing documents and precedent templates.

To start, obtain permissions to use the Tenant Copilot interface.

To configure a custom Document Generation model using Model Maker:

1. Prepare the training data (base template and final version of the document, along with any changelog or specifications)

2. Connect to Data Sources (SharePoint)

3. Use Model Maker to fine-tune the model

4. Train the Document Generation model

5. Evaluate the model and refine by better labeling or narrowing the training scope

6. Publish the model

The training process begins with inputting "precedent documents" and resulting versions of these "target documents" into Tenant Copilot to train the model. Instructions give directions for the specific changes to be made from the precedent to the target documents. During training, Target Copilot learns how to apply these changes to generate target documents. Once trained, users can input future change instructions to generate new versions of documents.

To configure the Document Generation model:

Prepare the training data.

1. Obtain permission to access the Copilot Studio Model Maker app to use the interface. This must be granted in the Settings page to unlock the app.

2. Ensure training data is available in either SharePoint, or stored within a supported connector.

   a. Precedent base template documents (either .pdf or .docx file formats) to provide starting contexts.

   b. Target final versions of the document (.docx or text-based .pdf file formats).

   c. Change logs or specifications (either .pdf or .docx file formats).

With the training data prepared, proceed to modeling.

Connect to data sources:

1. In Copilot Studio Model Maker interface, create a new model, as shown here:

  :::image type="content" source="placeholder-media" border="false" alt-text="On the Model Maker page, select + Add and give the Model a Name.":::

   a. Specify the name and provide a description.

   b. Set the task type to **Document Generation**.

   c. Provide **Model Instructions** about the use-case, tone, and style (specifying if this should be legal tone, organization specific constraints). Instructions allow for Copilot to learn the style and tone of your documents to ensure relevancy.

  :::image type="content" source="placeholder-media" border="false" alt-text="Screenshot showing Create New Model page with model instructions applied.":::

2. Go to the Copilot Studio **Permissions** page and grant permissions for who can use the Model.

3. In the **Data Sources** tab, select the SharePoint instance or custom connector where training data resides.

4. Ensure uploaded files are in .pdf or .docx file format.

   a. Supported file types are .pdf or .docx.

   b. Each document must include the necessary training data tab that consists of both the template used for the training, the resulting document or target versions of the document, and any change logs or specifications.

Label the data:

5. Select which documents from the uploaded files to use, and begin labeling.

6. The AI will identify potential document pairs by first identifying unique identifiers and common document elements.

   a. Providing training data helps Tenant Copilot learn the context of the documents and the style and tone used across the different versions.

7. View the identified pairs in **View all candidates** section.

  :::image type="content" source="placeholder-media" border="false" alt-text="Screenshot showing View all candidates section.":::

8. Review the pairs provided by Copilot and determine if you approve or reject the doc pairs.

   a. When approving doc pairs, verify the precedent document (left) and target document (right) match and approve accordingly.

  :::image type="content" source="placeholder-media" border="false" alt-text="Screenshot showing document pairs and how to reject or approve them.":::

   b. When rejecting a pair of documents as unrelated, adjust **View all candidates** section and approve more pairs for training data.

9. Evaluate the **Document Generation** model.

Train the Document Generation model:

10. Once sufficient data pairs have been provided (minimum of 10 pairs), the **Train Model** button will light up, and proceed by clicking.

11. Tenant Copilot will train the current model by analyzing changes made from the precedent base template documents, with any provided change logs in the supplementary field, to the target versions of the documents.

12. Once training has been completed, click **View Trained Model**.

13. Evaluate a sample of generated documents based on training supplied.

14. Reject the generated sample results and if model training evaluation doesn't meet desired standards.

15. Continue refining model based on sample evaluation results, by providing more document pairs or narrowing training scope.

16. Re-train model until document generation results meet expectations.

17. Evaluate the model and insure compliance with legal standards, style tones, tone context.

Publish the model:

18. Make the model available in the tenant by publishing under the tenant-wide permissions.

   a. **Publish Model** button will light up once training quality constraints are met.

  :::image type="content" source="placeholder-media" border="false" alt-text="Screenshot showing Publish Model button.":::

19. Deploy model by selecting Publish Model button.

20. Once successful deployment has been made, go to the Permissions tab on the Model Maker page.

21. Use the Share with users button to ensure that the trained model is applied within the tenant environment.

   a. Instruct end users—you—on how to effectively use the model in future iterations to prevent training drift.

  :::image type="content" source="placeholder-media" border="false" alt-text="Screenshot showing Share with users page.":::

22. Develop a Copilot Agent based off the output model results.

   a. End user only sees final output documents.

   b. Copilot Agents can be deployed through Microsoft 365 application interfaces, like Teams.

Further refinement and evaluation of specific data pairs can be done to narrow the context for the document generation model, providing better document specific results based on industry specific document generation use-cases. Evaluate the model regularly to ensure compliance with legal standards, style tones, tone context, and revise instructions accordingly.

Tenant Copilot avoids hallucination by working from industry specific rules derived from training data. It can only apply legal specific context already learned from training and instructions given to train model. With regular re-training, document generation capabilities can be refined for specific document legal standards. Once trained, a Copilot agent feature can be built to effectively support document creation workflows for legal specific industries similar to other models created in [Copilot Studio](placeholder-url).

For further learning about how fine-tuning models works, see [Fine tuning learnings](placeholder-md-file).

## Clean up Resources

No clean up resources is necessary, although certain connectors may present opportunities for cleaning up stored data. Ensure you follow your organization's data clean up policies to delete documents where model is trained from in certain scenarios.

## Next Steps or Related Content

Once a model is configured for document generation, deploy an Agent to streamline document generation workflows.

For more information, see [How to deploy document generation Copilot capabilities](placeholder-url).

If the document generation model doesn't work, refine the model by re-training using further documents or narrow the focus of training scope.

For more information, see [Refine Document Generation Models](placeholder-md-file).

> [!IMPORTANT]
> How To articles provide step-by-step instructions for completing a task. How To articles should be extremely task-focused and procedural. The outcome is job-based, so the steps lead the user to an outcom
