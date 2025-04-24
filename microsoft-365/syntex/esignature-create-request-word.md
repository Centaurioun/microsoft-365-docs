---
title: Create a signature request from Word in SharePoint eSignature
ms.author: chucked
author: chuckedmonson
manager: jtremper
ms.reviewer: amcdonnell
ms.date: 04/25/2025
audience: enabler
ms.topic: how-to
ms.service: microsoft-syntex
ms.subservice: syntex-content-intelligence
search.appverid: 
ms.collection: 
    - enabler-strategic
    - m365initiative-syntex
ms.localizationpriority: medium
description: Learn how to use SharePoint eSignature to create and send electronic signature requests from a PDF file to people inside and outside of your organization. 
---

# Create a signature request from Word in SharePoint eSignature

## Process considerations for Word

When you request electronic signatures from Word, the recipients will sign a PDF copy of the Word document.

- Recipients do not access the source Word document during the signing process.
- Recipient information, such as an email address, is not stored in the Word document.
- When signing is complete, the signed PDF will be stored in the same location as the Word document.
- Requests can be sent from editable Word documents and read-only Word documents that have pre-positioned eSignature fields placeholders.

## SharePoint eSignature for Word scenarios

- Create a request directly from a Word document. 
- Re-use the same document to create multiple requests.
- Create a template with pre-positioned eSignature fields.
- Create a request from an eSign template.
- Multiple users can create requests in parallel.

## Prerequisites

- A subscription version of Word desktop.
- User is on the Microsoft 365 Beta Channel or Current Channel.
- The document is stored in a SharePoint library.
- Recipients are access to the library.
- The document is in .docx format.
- The document is unencrypted.

# Create a signature request from Word

Follow these steps to use SharePoint eSignature for Microsoft Word.

1. Open a document from a SharePoint eSignature enabled site in Word (Desktop).

2. On the Word **Insert** ribbon, select **eSignatures fields**.

    ![Screenshot of the eSignature fields option on the Insert ribbon in Word.](../media/content-understanding/esignature-fields-option-word.png)

3. From the side panel, select **Add recipient**.
  

4. Add one or more recipients to sign the document.
 


5. Select the document location where you want to add an eSignature field. From the side panel, select **Insert** to add signature fields to the document.

6. The fields are inserted at the location of the insertion point in the document canvas.

7. Repeat step 5 for all fields you want to be inserted into the document.

8. Optionally, you can add a note.


9. Select **Create request**.
 
10. A PDF of the Word document is automatically created for recipients to sign.

## Tips (TBD)

- Insert the control into a text box
- Move a placeholder
- Delete a placeholder
- Add a placeholder
- Create a text box, insert placeholder. Do not move placeholder.
