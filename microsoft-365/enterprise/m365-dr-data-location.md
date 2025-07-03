---
title: Learn More about The Data Location Card
description: Learn More about The Data Location Card
ms.author: scotv
author: fhasen-msft
manager: bpardi
ms.service: microsoft-365-enterprise
ms.subservice: advanced-data-residency
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 02/24/2025
ms.reviewer: fahasen
ms.custom:
- it-pro
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- must-keep
---

# Learn More about The Data Location Card

This article is designed to help you understand how you can determine where your committed customer data for Microsoft 365 services is currently stored at rest, and where, if applicable, there are data residency commitments.

## Locating Where your _Tenant’s_ Data is Stored at Rest

The _Data Location Card_ (DLC) in the Microsoft 365 admin center allows _Tenant_ administrators (Microsoft 365 Admins or Global Amins) to see where their _Microsoft 365 Core Workloads_ and _Microsoft 365 Expanded Workloads_ Customer data is stored at rest for certain Microsoft 365 services. To access the _Data Location Card_, select the "Data location" section in the Microsoft 365 admin center portal by navigating to **Admin** > **Settings** > **Org settings** > **Organization profile** > **Data location**.

## Overview of the “Data at Rest” Locations

The _Data Location Card_ will display three columns outlining the covered _Services_, the _Current Geography_, and the _Committed Geography_.

The _Current Geography_ refers to the location where the in-scope customer data is currently stored, while the _Committed Geography_ refers to the location where Microsoft will store in-scope customer data based on the [data residency commitments applicable to the _Tenant_](m365-dr-overview.md#overview-of-data-residency).

## Finding The Commitments Applicable to a Workload
It is important to note that different workloads may be covered by different commitments depending on several factors, including the date of a customer’s subscription, the date that a _Tenant_ was provisioned, the _Default Geography_ of a _Tenant_, and if _Product Terms_ apply to certain workloads.

For simplicity, the _Data Location Card_ only displays a single _Committed Geography_ based on a _Tenant’s_ various commitments.

For example, if a _Tenant_:
- Has Microsoft 365 Multi-Geo data residency offering, then the new _Data Location Card_ experience will not be enabled. This is because the Microsoft 365 Multi-Geo offering allows tenant administrators to store data in multiple locations. For more information, please see the [Microsoft 365 Multi-Geo page](microsoft-365-multi-geo.md).
- Has an active ADR subscription, then _Committed Geography_ will reflect the _Local Region Geography_ that is associated with the _Tenant’s_ ADR commitment.
- Does not have ADR and qualifies for _Product Terms_ data residency [insert link], the applicable _Geography_ associated with the _Tenant’s_ _Product Terms_ will be listed.
- Does not have ADR and does not qualify for _Product Terms_ data residency [insert link], but the _Tenant’s_ Sign-up country is in the European Union or EFTA, then the _Tenant’s_ _Committed Geography_ will be the European Union/EFTA.

If a _Tenant_ does not have any of the above conditions, Microsoft will store the _Tenant’s_ information where it is most prudent for business operations, and that data storage location is subject to change without notice, and the DLC will display “No Commitment”.

_Tenants_ with an ADR commitment will see data location details for Microsoft 365 workloads included as part of the [Advanced Data Residency commitment](m365-dr-commitments.md).

_Tenants_ without ADR may see [other commitments](m365-dr-overview.md#table-3-available-data-residency-by-countryregion), if applicable, listed under the “Commitments” section.

In the event that a workload has more than one commitment, each commitment will be shown in the “Commitments” section of the _Data Location Card_.

<insert screenshot>

## Understanding Mismatches Between Current Geography and Committed Geography

A discrepancy may appear between _Current Geography_ and _Committed Geography_ in certain circumstances. For example:
1. **A customer has procured an Advanced Data Residency (ADR) commitment and has not yet opted-in to migration.** If a _Tenant_ has not yet opted-in to migration, the _Data Location Card_ will show a mismatch between _Committed Geography_ and _Actual Geography_. To rectify this discrepancy, the Tenant Administrator (Microsoft 365 Admin or Global Admin) must opt-in to migration and allow sufficient time for the migration to occur (see #2 below).
1. **A customer has recently procured an Advanced Data Residency (ADR) commitment on data location and has opted in to migration.** While the _Tenant’s_ _Committed Geography_ will update to reflect the _Tenant’s_ new commitment, it will take some time for the workloads to process the request and migrate data to the new location. _The Data Location Card_ will continue to display a mismatch between _Current Geography_ and _Committed Geography_ until the data migration effort is complete.  
    1. Example: A _Tenant's_ DLC displays a _Current Geography_ of “European Union/EFTA” but the customer recently purchased ADR for Spain. After opting-in to data migration, the _Tenant’s_ _Committed Geography_ will update to “**Spain**”; however, the _Tenant’s_ _Current Geography_ will continue to display “European Union/EFTA” until the _Tenant’s_ in-scope customer data has been migrated. When an individual workload completes data migration efforts, the _Data Location Card_ will update and display a _Current Geography_ of “**Spain**”.
    1. <insert screenshot>
1. **Data residency based on _Product Terms_ apply, but a _Tenant_ did not elect to take part in the _Legacy Move Program_.** If a Tenant is eligible for data residency based on _Product Terms_, but the Tenant Administrator did not elect to participate in the _Legacy Move Program_, the DLC may display a mismatch between _Current Geography_ and _Committed Geography_. In these cases, in order to migrate in-scope customer data to the _Tenant's_ corresponding _Local Region Geography_, a customer must first procure ADR licenses.
1. **A _Durable Commitment on Data Location_ has expired.** If a customer’s _Tenant_ was once covered by a _Durable Commitment on Data Location_, and that customer is no longer eligible for data residency based on the eligibility section for that _Durable commitment_, the DLC will reflect this change in the _Committed Geography_ location.
    1. Example: A customer _Tenant_ elected to stop renewing their ADR licenses that were used to ensure that data is retained in Italy. At the end of the license terms and grace period, the customer will see the _Committed Geography_ change from “**Italy**” to “**European Union/EFTA**”.
    1. <insert screenshot>
1. **The workload _Current Geography_ is located within a _Local Region Geography_, but _Committed Geography_ is located within a _Macro Region Geography_.** In this case the _Tenant_ data is being stored in alignment with the _Committed Geography_, but information about the _Tenant's_ current data location is more granular and information on the specific country or set of countries is made available in the _Current Geography_ field.
    1. Example: A _Tenant_ with a _Current Geography_ of “**France**” with a _Committed Geography_ of “**European Union/EFTA**”.
    1. <insert screenshot>
1. **A Committed Geography is not displayed displays “No Commitments”.** In this case, information about a _Tenant’s_ _Current Geography_ is accurate, and the _Tenant_ simply does not have any _Durable Commitments_ on Data Location_.
    1. Example: A _Tenant_ in Laos will see a _Current Geography_ where their data is currently stored, and “No Commitment” in the _Committed Geography_ location.
    1. <insert screenshot>
    1. In the event that a _Tenant_ does not have an existing _Durable Commitment on Data Location_ or there is no data center located in the region associated with the _Tenant’s_ Sign-up Country, the _Tenant’s_ data is not explicitly guaranteed to reside in any particular data center. In these cases, Microsoft will store the _Tenant’s_ information where it is most prudent for business operations, and that data storage location is subject to change without notice.
    1. Customers that wish to obtain a _Durable Commitment on Data Location_ for their _Tenant_ should refer to [Advanced Data Residency (ADR)](m365-dr-commitments.md) or [Multi-Geo Data Residency](microsoft-365-multi-geo.md). To determine if a customer is eligible for the _Product Terms_ commitment, see the [Product Terms Data Residency page](m365-dr-product-terms-dr.md).
    1. <insert screenshot>
1. **Workloads without Data** If the DLC displays a "-" next to a _Workload_, this indicates that a _Tenant_ does not currently have an active subscription for this service.
    1. <insert screenshot>
    1. In this example, the _Tenant_ does not have an active Microsoft 365 Copilot subscription.

## FAQ

**Why do I see multiple commitments for the same workload?**
_Tenants_ with an ADR commitment will only see the breakout of _Workloads_ for the Advanced Data Residency commitment.

_Tenants_ without ADR may see other commitments, if applicable, listed under the “Commitments” section. In the event that a workload has more than one commitment, each commitment will be shown in the “Commitments” section of the Data Location Card.
