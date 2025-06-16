---
title: "Troubleshoot the Copilot Tuning document generation tool FAQ"
f1.keywords:
ms.author: danielabo
author: danielabom
manager: calvind
ms.date: 06/10/2025
ms.topic: troubleshooting
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- m365copilot
- magic-ai-copilot
description: Contains reference transcript and how to write troubleshooting articles.
---

# Troubleshoot the Copilot Tuning document generation tool FAQ

This article describes some of the most common issues with the Copilot Tuning document generation tool FAQ and how to troubleshoot them.

[!INCLUDE [copilot-tuning-preview](includes/copilot-tuning-preview.md)]

## I'm unable to locate the correct SharePoint site for my knowledge sources

If you can't find the SharePoint site containing the files you need in Step 4, please contact your IT administrator. You might need permission to view those files.

## The preparation steps are taking too long

Sometimes, service queues might experience delays, impacting document processing times. In addition, resume processing might delay in updating the UI, making the issue appear unresolved. If the preparation process has taken over 10 minutes to complete, try refreshing the page, as it might be a bug in the UI platform. Otherwise, check for potential errors in the processing logs.

## I'm seeing an error during the data extraction process

If an error occurs during knowledge source extraction, click the **Models** link on the left side navigation panel to view the list of files in your model. Check the status in the right-side column to identify errors in copying SharePoint data into Heron.

## The Excel file is empty, and I can't label any data

I recommend verifying whether you are configuring the knowledge sources correctly and uploading a clean Excel file again. If the problem persists, contact the team for assistance.

## The evaluation report for the model is negative

I recommend improving the model instructions iteratively to prevent common errors in tenant document generation or summarization models. Adding more data, fixing labeling issues, or addressing data setup problems might help improve accuracy.

## I'm encountering issues when trying to upload my labels

To resolve this issue, follow these steps

1.  Download a clean Excel file from the current application state.
2.  Correct the sheet.
3.  Retry uploading the file.

## There's a formatting or validity issue with the final Word document

I recommend improving the model instructions to prevent common errors in tenant document generation or summarization models. Adding more guardrails might help prevent tenant-specific formatting issues.

## The generated documents differ from the training data

Check the format of the input data to ensure it matches the data used during model training.


## Related Content

[Placeholder for related articles and resources.]
