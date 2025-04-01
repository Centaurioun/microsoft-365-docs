---
title: Manage expiring agreements in SharePoint Agreements
ms.author: chucked
author: chuckedmonson
manager: jtremper
ms.reviewer: vbarla
ms.date: 04/02/2025
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

# Manage expiring agreements in SharePoint Agreements

When managing agreements, it's important to keep track of their expiration dates to ensure timely renewals and avoid lapses.

The **Expiration date** is a standard field that records the date an agreement is set to expire. This field should be included in any template designed for agreements that have an expiration date. When the **Expiration date** field is filled in the agreement, the following actions occur:

**Two months before the expiration date:**

- A reminder notification is sent to the appropriate recipients, indicating the specific date the agreement will expire.

- This notification will be sent weekly for the two months leading up to the expiration date.

**On the expiration date:**

- A notification is sent to the appropriate recipients, informing them that the agreement has expired.

- The status of the agreement is updated to **Expired**.

> [!NOTE]
> To ensure the expiration notification is sent to a specific person or group, include the **Owner** field in the template and designate the appropriate recipients during the document authoring stage.