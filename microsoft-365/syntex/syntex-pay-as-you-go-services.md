---
title: Pay-as-you-go pricing for document processing for Microsoft 365
ms.author: chucked
author: chuckedmonson
manager: jtremper
ms.reviewer: ssquires, kkameth
ms.date: 08/01/2025
audience: admin
ms.topic: article
ms.service: microsoft-syntex
ms.collection: 
    - essentials-get-started
    - m365initiative-syntex
    - Tier1
search.appverid: MET150
ms.localizationpriority: medium
description: Learn about pay-as-you-go pricing for document processing services for Microsoft 365.
---

# Pay-as-you-go pricing for document processing for Microsoft 365

> [!NOTE]
> Through December 2025, if you have [pay-as-you-go billing](syntex-azure-billing.md) set up, your organization receives a limited amount of included capacity each month for selected services, letting you try these services at no cost. This offering doesn't include capacity for Microsoft 365 Archive or Microsoft 365 Backup. For more information, see [Try out pay-as-you-go document processing services](promo-syntex.md).

When you use pay-as-you-go services, you're billed using service meters in the Azure subscription that you specified when you [set up pay-as-you-go billing](syntex-azure-billing.md#connect-the-service-to-an-azure-subscription-for-billing).

To help your organization in planning for pay-as-you-go services, you can use the [SharePoint cost calculator](https://aka.ms/SharePoint/PAYG-Calculator). This tool gives you a better understanding of your organization’s usage patterns and estimated costs so you can make more informed decisions.

> [!NOTE]
> While these services leverage an Azure subscription for billing purposes, they do not apply to the [Microsoft Azure Consumption Commitment (MACC)](/marketplace/azure-consumption-commitment-benefit) that your organization might have.

The following tables describe each meter, its pricing, and how it measures usage. When you connect your Azure subscription to pay-as-you-go services, users in your organization are able to take advantage of document processing services right away. Your tenant is billed according to the details shown in this article.

## Document processing services

|Service|What's counted?|What's billed? (USD)|
|:----|:--------------|:-------------|
|**[Autofill columns](autofill-overview.md)** |The number of pages processed for Word, PDF, or TIFF files; the number of sheets for Excel files; the number of slides for PowerPoint files; or the number of files for other file types. Each of these counts as one transaction. Cost is the same for one or more prompts per page. |$0.005/transaction |
|**[Document translation](translation-overview.md)** |The number of characters processed. Character count includes letters, Unicode code points, punctuation, and white spaces. |$15.00/1M characters |
|**[eSignature](esignature-overview.md)** |The number of electronic signature requests created. Up to 10 recipients can be included in each request. |$2.00/request |
|**[Optical character recognition](ocr-overview.md)**  |The number of pages processed for images (JPEG, JPG, PNG, or BMP); the number of pages processed for PDF, TIF, or TIFF; or the number of embedded images in Teams chats and email messages. Each of these counts as one transaction. Processing occurs every time the file is edited. |$0.001/transaction|
|**[Content assembly](content-assembly.md)** |The number of documents (Word or PDF) created using templates. Each processed document counts as one transaction.<br><br>If you have an existing per-user license, you won't be charged for generating documents manually but will be charged for automated document generation using Power Automate. |$0.15/transaction |
|**[Image tagging](image-tagging-overview.md)** |The number of images processed. Each processed image counts as one transaction. You won’t be charged if you only enable pay-as-you-go billing for image tagging. You're charged only when you [enable image tagging on a document library](image-tagging.md). |$0.001/transaction |
|**[Taxonomy tagging](taxonomy-tagging-overview.md)** |The number of documents processed. Each processed document counts as one transaction. You won’t be charged if you only enable pay-as-you-go billing for taxonomy tagging. You're charged only when you [enable taxonomy tagging on a document library](taxonomy-tagging.md). |$0.05/transaction |
|**[Prebuilt document processing](prebuilt-overview.md)**|The number of pages processed for PDF or image files. Each of these counts as one transaction. You won't be charged for model training. You're charged for processing whether or not there's a positive classification, or any entities extracted.<br><br>Processing occurs on document upload and on subsequent updates. Processing is counted for each model applied. For example, if you have two models applied to a library and you upload or update a five-page document in that library, the total pages processed is 10.|$0.01/transaction|
|**[Structured and freeform document processing](form-processing-overview.md)**|The number of pages processed for PDF or image files. Each of these counts as one transaction. You won't be charged for model training. You're charged for processing whether or not there's a positive classification, or any entities extracted.<br><br>Processing occurs on document upload and on subsequent updates. Processing is counted for each model applied. For example, if you have two models applied to a library and you upload or update a five-page document in that library, the total pages processed is 10.<br><br>If you have AI Builder credits allocated to the environment, these credits are used first. Once the credits are exhausted, the processing transactions are charged to the meter.|$0.05/transaction|
|**[Unstructured document processing](document-understanding-overview.md)**|The number of pages processed for Word, PDF, or TIFF files; the number of sheets for Excel files; the number of slides for PowerPoint files; or the number of files for other file types. Each of these counts as one transaction. You won't be charged for model training. You're charged for processing whether or not there's a positive classification, or any entities extracted.<br><br>Processing occurs on document upload and on subsequent updates. Processing is counted for each model applied. For example, if you have two models applied to a library and you upload or update a five-page document in that library, the total pages processed is 10.|$0.005/transaction|

## Storage services

|Service|What's counted?|What's billed? (USD)|
|:----|:--------------|:-------------|
|**[Microsoft 365 Archive](/microsoft-365/archive/archive-overview)**  |The number of gigabytes (GB) of data archived. (This meter is only charged when archived storage plus active storage in SharePoint exceeds a tenant’s included or licensed allocated SharePoint storage capacity limit.) <br>**For OneDrive only**, the number of GBs of archived data reactivated. <br><br><sup>**NOTE**: Education organizations are billed at $0.02/GB/month for the data archived. This meter is only charged when archived storage in SharePoint plus active pooled storage usage exceeds a tenant’s pooled storage capacity limit. For more information, see [Education offering](../archive/archive-education-offering.md).</sup>    |$0.05/GB/month (shows on invoice as $0.00167/GB/day)<br><br>$0.60/GB|
|**[Microsoft 365 Backup](/microsoft-365/backup/backup-overview)**  |The number of gigabytes (GB) of data backed up. |$0.15/GB/month (shows on invoice as $0.005/GB/day)|

## Video services

|Service|What's counted?|What's billed? (USD)|
|:----|:--------------|:-------------|
|**[Video translation](https://support.microsoft.com/office/2e34ad1b-e213-47ed-a806-5cc0d88751de)** |The number of characters from the source transcript. (This meter is charged only when the translation has successfully resulted in a new transcript.) |$15.00/1M characters |
