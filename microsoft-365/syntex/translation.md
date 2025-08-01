---
title: Translate a document
ms.author: chucked
author: chuckedmonson
manager: jtremper
ms.reviewer: ssquires
ms.date: 08/01/2025
audience: admin
ms.topic: how-to
ms.service: microsoft-syntex
ms.subservice: syntex-content-intelligence
search.appverid: 
ms.collection: 
    - enabler-strategic
    - m365initiative-syntex
ms.localizationpriority:  medium
description: Learn how to translate documents using SharePoint.
---

# Translate a document

Document translation lets you create a translated copy of a file manually on demand or automatically by using rules. You can set a rule to create a translated copy automatically when a document is created, or when data in a column is modified.​

When a file is translated, the file name of the translated copy is appended to show the ISO code for the language.

   ![Screenshot showing the translated filename with the language code appended.](../media/content-understanding/translation-file-with-language-code.png)

## Translate a document on demand

To create a translated version of a document, follow these steps:

1. From a SharePoint document library ([or from OneDrive](/sharepoint/onedrive-document-translation)), select the file or files you want to translate. Then use either of the following methods to start the translation process.

   - From the ribbon, select **More options** (**...**), and then select **Translate**.

       ![Screenshot showing the Translate option from the ribbon.](../media/content-understanding/translation-ribbon-option2.png)

   - Or, next to the file name in the list of documents, select **More actions** (**...**), and then select **Translate**.

       ![Screenshot showing the Translate option next to the document.](../media/content-understanding/translation-show-more-actions.png)

2. On the **Translate documents** screen, under **Languages**, select the language or languages you want to use from the drop-down menu or enter them manually. You can choose up to 10 languages.

   ![Screenshot showing the Translate documents screen with language options.](../media/content-understanding/translation-translate-documents-languages.png)

3. If you want to use a [custom glossary file](translation-glossary.md) for the translation, under **Translation glossary**, select the glossary file or [add a link to the file](translation-glossary.md#link-to-a-glossary-file). The option to add a glossary is only available when you are translating one language at a time.

   ![Screenshot showing the Translate documents screen with translation glossary options.](../media/content-understanding/translation-translate-documents-glossary.png)

4. Select **Translate**.

5. You receive a confirmation message saying that the request to translate the file has been submitted.

   ![Screenshot showing the translation confirmation screen.](../media/content-understanding/translation-confirmation.png)

   It can take several minutes for the translated file to be created. When the process is completed, the translated file will appear in the document library.

   If you try to submit a duplicate translation request before the file has finished processing, you'll receive a message telling you to wait a few minutes before trying again.

   ![Screenshot showing the message to wait a few minutes and trying again.](../media/content-understanding/translation-wait-message.png)

## Translate a document automatically

You can create a rule to automatically translate a document [when a new file is added](content-processing-translate.md#translate-a-document-when-a-new-file-is-added) or [when data in a column changes](content-processing-translate.md#translate-a-document-when-data-in-a-column-changes). For step-by-step instruction, see [Create a rule to translate a document](content-processing-translate.md).

## View the processing status

You can view real-time updates on files processed for document translation on the **Translation activity** panel. For more information, see [Monitor the status of files processed for autofill and translation in SharePoint](processing-status-ai.md).

## Translate a video transcript

To create a translated version of a video transcript or closed captioning, see [How to translate transcripts in Stream for SharePoint](https://support.microsoft.com/office/microsoft-syntex-pay-as-you-go-transcript-translations-in-stream-for-sharepoint-2e34ad1b-e213-47ed-a806-5cc0d88751de#bkmk_howtotranslate).

## Give feedback on translated documents

You can quickly provide feedback on translated files directly within your document library. When viewing a translated file in the library, hover over the file name to access the file card. Use the thumbs up (👍) or thumbs down (👎) icon to rate the translation quality.

![Screenshot of the feedback notification for translation.](../media/content-understanding/translation-feedback-1.png)

After selecting an icon, you’ll be prompted to:

- Rate the feature
- Add comments
- Optionally, attach the source or translated documents
- Opt in to include diagnostic logs
- Opt in to allow Microsoft to follow up with you

![Screenshot of the submit feedback to Microsoft screen.](../media/content-understanding/translation-feedback-2.png)

Your feedback helps us improve the translation experience.

<!---
Use the thumbs up (![Image of the thumbs up icon.](../media/content-understanding/icon-thumbs-up.png)) 👍 or thumbs down (![Image of the thumbs down icon.](../media/content-understanding/icon-thumbs-down.png)) 👎 icon to rate the translation quality.
--->