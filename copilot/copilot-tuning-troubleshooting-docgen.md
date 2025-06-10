---
ms.topic: troubleshooting
title: Troubleshooting FAQ
description: Contains reference transcript and how to write troubleshooting articles.
author: jasonjoh
ms.author: jasonjoh
ms.date: 06/04/2025
manager: calvind
---

This document contains:

- A troubleshooting FAQ for a Tenant Copilot document generation tool.
- Guidelines to assist **the schema** on how to write a troubleshooting article.

## Troubleshooting FAQ

Below are some tips to resolve issues encountered during various stages of the document generation and summarization process. If you're experiencing other problems, please [contact support](placeholder-md-file).

| Question | Response |
| - | - |
| I'm unable to locate the correct SharePoint site for my knowledge sources. What should I do? | If you can't find the SharePoint site containing the files you need in Step 4, please contact your IT administrator. You might need permission to view those files. |
| Why is the preparation step taking a long time? | If the preparation process has taken over 10 minutes to complete, try refreshing the page, as it might be a bug in the UI platform. Otherwise, wait for a while longer to see if processing finishes. [Meeting transcript](placeholder-md-file) |
| I'm seeing an error during the data extraction process. What should I do? | If an error occurs during knowledge source extraction, click on the "Models" link on the left side navigation panel to view the list of files in your model. Check the status in the right-side column to identify errors in copying SharePoint data into Heron. [Meeting transcript](placeholder-md-file)
| The Excel file is empty, and I can't label any data. | I recommend verifying whether you are configuring the knowledge sources correctly and uploading a clean Excel file again. If the problem persists, contact the team for assistance. [Meeting transcript](placeholder-md-file)
| The evaluation report for the model is negative. | I recommend improving the model instructions iteratively to prevent common errors in tenant document generation or summarization models. Adding more data, fixing labeling issues, or addressing data setup problems might help improve accuracy. [Also consider related chat transcript](placeholder-md-file) |
| I'm encountering issues when trying to upload my labels. | First, download a clean Excel file from the current application state. Correct the sheet and retry uploading the file. [Meeting transcript](placeholder-md-file)
| There's a formatting or validity issue with the final Word document. | I recommend improving the model instructions to prevent common errors in tenant document generation or summarization models. Adding more guardrails might help prevent tenant-specific formatting issues. [Meeting transcript](placeholder-md-file)
| The generated documents differ from the training data. | Check the format of the input data to ensure it matches the data used during model training. [Meeting transcript](placeholder-md-file)

## Potential Quick Workarounds

1. **Verify Permissions:** Ensure you have the necessary permissions to access the required SharePoint sites. Contact your IT administrator to adjust permissions if necessary.

2. **Processing Delays:** If the document preparation step takes longer than expected, refresh the page or wait a few more minutes to see if it completes. If not, check for potential errors in the processing logs.

3. **Data Extraction Verification:** Double-check the status of your data extraction process in the model list. Ensure there are no errors related to copying data from SharePoint to Heron.

4. **Review Excel Configuration:** If encountering issues with labeling or empty Excel files, verify the configuration and re-upload a clean Excel file if needed.

5. **Upload Procedure:** Trouble uploading labels can often be resolved by downloading a fresh template, ensuring data accuracy, and then attempting the upload again.

By following these quick workarounds, users can resolve common issues swiftly, allowing them to continue with the document generation process without major disruptions.

## Troubleshooting Checklist

### Troubleshooting Step

If you're facing issues with model preparation steps failing, consider the following measures:

1. **Service Delays:** Sometimes, service queues might experience delays, impacting document processing times. In addition, resume processing might delay in updating the UI, making the issue appear unresolved.

2. **Data Processing Errors:** Errors in data processing can occur during setup or configuration stages. Review the setup steps and correct any discrepancies.

Refer to the [meeting transcript](placeholder-md-file) or the [related chat transcript](placeholder-md-file) for more context on solving these issues.

## Causes and/or Solutions

### Troubleshooting Checklist

1. Problems with data extraction during knowledge source configuration.
2. Empty Excel file for labeling needs verification of knowledge source setup.
3. Negative evaluation reports require detailed examination of model instructions.
4. Issues with uploading labels necessitate downloading and correcting the Excel file.
5. Problems with the final Word document's formatting need consideration of model instructions.
6. Discrepancies between model output and training data require careful review.

Addressing these issues methodically ensures smoother troubleshooting and model configuration process.

### Solution

1. **SharePoint Site Access:** If you're unable to locate the correct SharePoint site, get in touch with your IT administrator to revise your permissions.

2. **Data Extraction Problem:** Check the "Models" list and status column to verify the handling of your data and identify any errors during data copying to Heron.

3. **Labeling Issues:** Review the Excel file configuration and contact them for assistance if needed.

4. **Evaluation Report Problem:** Iteratively improve your model instructions to enhance accuracy for document generation.

5. **Word Document Formatting Issue:** Refine model instructions with additional guardrails to prevent specific tenant formatting errors.

6. **Model Output Discrepancy:** Validate the format of your input data to ensure it matches the data used during model training.

## Advanced Troubleshooting and Data Collection

For advanced troubleshooting and data collection, consider:

1. **Check Model Output Discrepancy:** Ensure the input data matches the format used during model training.

2. **Additional Guidance:** Consult internal teams for advanced services to explore beyond basic troubleshooting.

By leveraging advanced steps, you can delve deeper into root causes, effectively improving your model's output accuracy.

## Related Content

[Placeholder for related articles and resources.]
