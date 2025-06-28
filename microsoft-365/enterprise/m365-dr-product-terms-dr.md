---
title: Overview of Product Terms Data Residency
description: Learn about Product Terms Data Residency
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.subservice: advanced-data-residency
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 02/11/2025
ms.reviewer: deanw
ms.custom:
- it-pro
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- must-keep
---

# Overview of Product Terms Data Residency

> [!NOTE]
> This document is intended to provide a general overview of the Microsoft Privacy and Security Product Terms in relation to data residency commitments. In the event of a discrepancy, the official terms listed on the [Privacy and Security Product Terms webpage](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all) shall prevail.

Microsoft Privacy and Security product terms included with Microsoft's Cloud product terms provides data residency commitment under the following conditions:

**Terms apply to**: _Tenants_ with a _Default Geography_, regardless of date of initial provisioning, of Australia, Brazil, Canada, France, Germany, India, Japan, Norway, Qatar, South Africa, South Korea, Sweden, Switzerland, the United Kingdom, the United Arab Emirates, United States and the European Union.

**Commitments Period**: The commitment period is equal to the length of the customer’s contract with Microsoft. Typically, this is 1-3 years.

[_Microsoft 365 Core Workloads_](m365-dr-overview.md#table-1-definitions-and-terms): Workloads covered by the Microsoft Privacy and Security product terms are:

| Workload | Date Added to Privacy and Security Terms |
|:-----|:-----|
|Exchange Online |Always Included |
|SharePoint |Always Included |
|OneDrive |Always Included |
|Microsoft Teams |Added November 1, 2022 |
|Microsoft 365 Copilot |Added March 1, 2024 |

The language at time of writing this article is:

- **Office 365 Services** If Customer provisions its tenant in Australia, Brazil, Canada, the European Union, France, Germany, India, Japan, Norway, Qatar, South Africa, South Korea, Sweden, Switzerland, the United Kingdom, the United Arab Emirates, or the United States, Microsoft stores the following Customer Data at rest only within that Geo: (1) Exchange Online mailbox content (e-mail body, calendar entries, and the content of e-mail attachments), (2) SharePoint site content and the files stored within that site, (3) files uploaded to OneDrive, (4) Microsoft Teams chat messages (including private messages, channel messages, meeting messages and images used in chats), and for customers using Microsoft Stream (on SharePoint), meeting recordings, and (5) any stored content of interactions with Microsoft 365 Copilot to the extent not included in the preceding commitments.
- For current language, refer to the [Privacy and Security Product Terms webpage](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all) and view the section titled "Location of Customer Data at Rest for Core Online Services."

For more data residency capabilities, refer to the [_Multi-Geo_ service](microsoft-365-multi-geo.md) and/or the [_Advanced Data Residency_ service](advanced-data-residency.md).

## FAQ

### Privacy and Security Product Terms Data Residency and Migration

**Data residency based on _Privacy and Security Product Terms_ apply, but your _Tenant_ did not elect to take part in the _Legacy Move Program_**. If your _Tenant_ is eligible for data residency based on _Privacy and Security Product Terms_, but did not elect to participate in the _Legacy Move Program_ you may see a mismatch between _Current Geography_ and _Committed Geography_. In these cases, your _Tenant_ is still eligible to retain data for _Microsoft 365 Core Workloads_ in the respective _Local Region Geography_ once it has migrated to that location. Data residency based on _Privacy and Security Product Terms_ does not currently include data migration into the _Local Region Geography_. In order to migrate the data, you must first procure ADR license(s).
