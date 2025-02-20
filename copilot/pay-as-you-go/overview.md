---
title: Microsoft 365 Copilot pay-as-you-go overview
description: Learn about the pay-as-you-go service for Microsoft 365 Copilot Chat and how you can enable consumption-based billing for Copilot.
ms.author: camillepack
author: camillepack
manager: scotv
ms.date: 02/20/2025
ms.reviewer: 
audience: Admin
ms.topic: get-started
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- scotvorg
- m365copilot
- magic-ai-copilot
- essentials-overview
ms.custom: [copilot-learning-hub]
---

# Microsoft 365 Copilot pay-as-you-go overview

The Microsoft 365 Copilot pay-as-you-go plan offers a flexible and cost-effective way for organizations to access Copilot services. This plan allows administrators to enable consumption-based billing for specific Copilot scenarios, providing users with the ability to use Copilot features without committing to a full license. This article provides an overview of the pay-as-you-go plan, its benefits, and pricing details.

## Why pay-as-you-go?

The Microsoft 365 Copilot pay-as-you-go plan offers a flexible and scalable solution for organizations looking to leverage AI capabilities without the commitment of a full license. By enabling consumption-based billing, administrators can better manage costs and provide users with access to powerful Copilot features as needed.

### Common use cases

- **Cost control** You can enable pay-as-you-go for specific users or scenarios, allowing for better cost management.
- **Establish usage patterns** Understand adoption patterns for new apps to determine whether prepaid licenses make financial sense for your business.
- **Scalability** Organizations can scale their usage based on demand, paying only for the consumption.

## How does it work?

The pay-as-you-go plan allows administrators to set up billing for Microsoft 365 Copilot Chat, enabling users to access declarative agents on a consumption basis. You can manage billing, view costs, and turn off services as needed.

The following administrator roles in the Microsoft 365 admin center can view and manage pay-as-you-go:

- Global administrator
- AI administrator
- Global reader (read-only access)

### Billing process

When you link your Azure subscription to a service for pay-as-you-go billing in the Microsoft 365 admin center, you're billed on a pay-as-you-go basis for the service you set up.

You can cancel or delete your subscription at any time to stop processing and billing.

### Process for new feature releases

In the future, new features using pay-as-you-go billing will be announced via a message center post. When the features become available, users in your organization will be able to take advantage of those capabilities. Pay-as-you-go billing is disabled by default. A global admin or owner to the subscription can enable or disable Microsoft 365 pay-as-you-go features in the Microsoft 365 admin center.

## Pricing details

When you use a Microsoft pay-as-you-go service linked to an Azure subscription, the service gets billed using the Azure subscription that you specified when you set up billing.

The following table describes the service, its pricing, and how it measures usage. When you connect your Azure subscription to the service you’ve set up for pay-as-you-go billing, users in your organization can take advantage of the service right away.
Your tenant is billed according to the details shown in the following table:

| Service   | Description    | What’s Counted?        | What’s billed? (USD) |
|----------------------------------|-----------------------------------------------------------------------------|----------------------------------|----------------------|
| Agents in Microsoft 365 Copilot chat | Use agents grounded in work data (work data in your tenant’s Microsoft Graph and 3rd party data via Graph connectors) | The number of messages used.     | $0.01/message        |

>[!NOTE]
> Each interaction includes a question and an answer. Successful interaction uses 32 messages.

## Monitoring and billing

The organization’s consumption of the pay-as-you-go service can be monitored on the [Cost Management](/microsoft-365/commerce/use-cost-mgmt) page in the Microsoft 365 admin center for each of the Microsoft 365 pay-as-you-go services that you use.

Billing for services is done through the Azure subscription that you associate to the service.

## Next step

[Meters](meters.md) (article)
