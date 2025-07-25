---
title: Create a signature request from a PDF in eSignature
ms.author: chucked
author: chuckedmonson
manager: jtremper
ms.reviewer: amcdonnell
ms.date: 08/01/2025
audience: enabler
ms.topic: how-to
ms.service: microsoft-syntex
ms.subservice: syntex-content-intelligence
search.appverid: 
ms.collection: 
    - enabler-strategic
    - m365initiative-syntex
ms.localizationpriority: medium
description: Learn how to use eSignature to create and send electronic signature requests from a PDF file to people inside and outside of your organization. 
---

# Create a signature request from a PDF in eSignature

## Create a signature request from a PDF

Use the following steps to start the eSignature process. You must be signed in to SharePoint by using your work email address.

> [!NOTE]
> Only unencrypted PDF documents are supported at this time.

1. From a SharePoint document library, open the document for which you want to start the eSignature process.

2. In the document viewer, select the pen icon.

    ![Screenshot of a document showing the Get signatures option.](../media/content-understanding/esignature-get-signatures-option-dark.png)

3. On the **Create a signature request** panel, add up to 10 internal or external recipients you want to sign the document. If the recipients need to sign in order, turn on the **Recipients must sign in order** toggle. You can change the order of the recipients by dragging and dropping them to the correct order. Then select **Next**.

    ![Screenshot of the Add recipients panel.](../media/content-understanding/esignature-add-recipients-panel-dark.png)

4. On the **Create a signature request** panel (step 2 of 3), drag and drop the **Signature**, **Initials**, and **Date** fields to the appropriate locations in the document for each recipient. Each form field can be marked either as required or not required.

    ![Screenshot of the Specify where to sign panel.](../media/content-understanding/esignature-add-form-fields-panel-dark.png)

5. Select **Next** to progress to the next stage. At least one required signature field is needed for each recipient. Up to 50 fields (total) can be added to the document.

6. On the **Create a signature request** panel (step 3 of 3), enter a title for the request, add an optional message, and review the details on the panel to make sure it's correct. Then select **Send**.

    ![Screenshot of the Review request panel.](../media/content-understanding/esignature-review-request-panel-dark.png)

    Once sent, the status of the request is set to **In progress**.  An email notification is sent to the creator and the recipients. If **Recipients must sign in order** is toggled on, recipients will be able to add their signature in the order specified, otherwise they can add their signature in any order.  

<!---
#### Processing notifications

When you create a request, you receive notifications that update you on the processing status.

- Notification that the request is processing

    ![Screenshot of the notification that the request is processing.](../media/content-understanding/esignature-notification-processing.png)

- Notification that you can access the PDF to review or sign

    ![Screenshot of the notification that the PDF is ready to review and sign.](../media/content-understanding/esignature-notification-processing.png)

You can create a new request without needing to dismiss the notification.

- Notifications that the initial request has been sent, and that a second request is processing

    ![Screenshot of notifications that a request has been sent and a second request is processing.](../media/content-understanding/esignature-notification-send-second-request.png)

You can also keep track of multiple requests with stacked notifications that can be dismissed.

- Each notification represents a distinct eSignature request

    ![Screenshot of notifications showing that two requests have been sent.](../media/content-understanding/esignature-notification-two-requests-sent.png)
--->

#### Track and manage other provider requests

Managing ongoing electronic signature requests for other providers is done on the provider website or through the Approvals app in Microsoft Teams. You'll also be notified by email from the provider throughout the signing process.

## Create a signature request using another provider

Use the following steps to start an electronic signature in SharePoint using another provider, such as Adobe Acrobat Sign or DocuSign.

1. From a SharePoint document library, open the document you want to start the eSignature process.

2. In the document viewer, select the eSignature icon, and then select the provider you want to use from the menu.

    ![Screenshot showing how to select a provider on the ribbon.](../media/content-understanding/esignature-select-provider.png)

3. You'll be prompted to sign in to the provider using your sign-in credentials the first time. For subsequent requests, you might not need to sign in again.

4. After successful sign in, you'll be prompted to continue on the provider's website.

5. The document is automatically transferred to the provider service.

6. The provider's website opens in another browser tab.

7. On the new tab, proceed with the request creation process as you normally would.

8. Once completed, you can close all document tabs.

9. To cancel or track a request from other providers, you can do this in the Approvals app in Teams or via the provider's website.

<br>

> [!div class="nextstepaction"]
> [Review and sign a request](esignature-review-sign-requests.md)
