---
title: Microsoft 365 Copilot Tuning document generation
f1.keywords:
ms.author: jasonjoh
author: jasonjoh
manager: calvind
ms.date: 06/10/2025
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- m365copilot
- magic-ai-copilot
description: Learn how to use Microsoft 365 Copilot Tuning to create fine-tuned LLMs based on your tenant data for document generation.
---

# Use Microsoft 365 Copilot Tuning to create fine-tuned LLMs for document generation

## Prerequisites

- A user account with the **Model Maker** role.
- Prepared training data hosted in a SharePoint document library, including:
  - Template or base documents
  - Examples of completed documents generated using the template or base documents
  - If available, documents or notes that describe what changed from the template or base documents to create the completed document

## Create the model

1. Open your browser and navigate to [Copilot Studio](https://copilotstudio.microsoft.com). Sign in with a user account with the **Model Maker** role.
<!-- markdownlint-disable MD033 -->
1. In the left-hand rail, select the ellipses (<kb>...</kb>), then select **Copilot tuning**.
<!-- markdownlint-enable MD033 -->
1. Select **Create a new model**.

1. Enter a clear, descriptive name for the model.

1. Enter a brief description of the model's purpose.

1. Select **Add knowledge**, then select **SharePoint**. Use the **Browse** button to find the SharePoint location of your training data, or paste the SharePoint site URL and select **Add**. When you have added all of your SharePoint locations, select **Add**.

1. Under **Permissions**, select security groups to grant access to your model.

1. For **Task type**, select **Document generation**.

1. Under **Model Instructions**, fill in answers to the questions about your training data and the desired output.

    - **How should the system refer to the original file?**: Describe the input files to help the model understand how to interpret the information.
    - **How should the system refer to the final file?**: Describe the desired output to help the model understand the purpose and format of the documents.
    - **How should the system refer to the files that describe what needs to change?**: Describe the documents or notes that describe what changed.
    - **What criteria should the system use to evaluate and validate the generated document output?**: Provide instructions and criteria for the desired output.

1. Select **Prepare labeling data**.

1. Wait for Copilot Tuning to process your training data before proceeding to the next step. You will receive an email when this process is finished, and the **Status** column of the model in Copilot Studio will update to **Ready for labeling**.

> [!NOTE]
> Processing your training data takes some time, depending on the number of files and complexity of the data.

## Label document pairs

