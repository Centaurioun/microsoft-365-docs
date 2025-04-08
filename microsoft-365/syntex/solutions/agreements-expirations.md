---
title: Manage expirations of agreements in SharePoint Agreements
ms.author: chucked
author: chuckedmonson
manager: jtremper
ms.reviewer: vbarla
ms.date: 04/09/2025
audience: admin
ms.topic: conceptual
ms.service: microsoft-syntex
ms.subservice: syntex-content-intelligence
search.appverid: 
ms.collection: 
    - enabler-strategic
    - m365initiative-syntex
ms.localizationpriority:  medium
ROBOTS: NOINDEX, NOFOLLOW
description: Learn about the expiration process for agreements in the SharePoint Agreements solution.
---

# Manage expirations of agreements in SharePoint Agreements

It's important to keep track of the expiration dates in agreements to ensure timely renewals and avoid lapses. The **Expiration date** is a standard field that records the date an agreement is set to expire. This field should be included by template creators in any template designed for agreements that have an expiration date and must be filled by agreement creators for the reports, notifications, and status changes to take effect.

To ensure that imported agreements follow the expiration flow, ensure that the **Expiration date** field is filled in the Agreement details screen when importing signed agreements.

![A screenshot of an agreement showing an expiration date is added.](../../media/content-understanding/agreements-expiration-date-added.png)

Once the agreement generated from the solution is signed and executed, or the imported agreement is successfully added after reviewing and confirming its details, the expiration date cannot be added or updated.

If the **Expiration date** is not included in the agreement, it will be treated as an evergreen agreement.


## Expiration notifications

When the **Expiration date** field is filled in the agreement, the following actions occur:

**Two months before the expiration date:**

- A reminder notification is sent to the [default recipients](#default-recipients-of-notifications), indicating the specific date the agreement will expire.

- This notification will be sent weekly for the two months leading up to the expiration date.

**On the expiration date:**

- A notification is sent to the [default recipients](#default-recipients-of-notifications), informing them that the agreement has expired.

- The status of the agreement is updated to **Expired**.

   ![A screenshot of a notification sent to inform recipients than an agreement is expired.](../../media/content-understanding/agreements-expired-agreement-notification.png)

### Default recipients of notifications

For agreements generated using the solution, the recipient is the agreement author or creator. For imported agreements, the recipient is the uploader of the agreement.

#### Considerations for manageing notifications

- To ensure the expiration notification is sent to a specific person or group other than the default recipient, include the **Owner** field in the template and designate the appropriate recipients during the agreement authoring stage.

- For the agreements in **Draft** status, the expiration notifications and status change will not be triggered.

- If an agreement's Word document is under the status of **Published**, **Reviewed**, or **Approved**, and it is downloaded, signed, and converted into a PDF using a third-party electronic signature tool, the following occurs:

    - The PDF is imported into the Agreements solution with the status **Active**, while the Word document remains in its original status.

    - As a result, two different expiration notifications will be sent: one for the Word document and one for the PDF.


<br>

> [!div class="nextstepaction"]
> [See the complete list of help documentation.](agreements-overview.md#help-documentation)
