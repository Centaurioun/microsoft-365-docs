---
title: Microsoft 365 Copilot pay-as-you-go overview
description: Learn about the pay-as-you-go service for Microsoft 365 Copilot Chat and how you can enable consumption-based billing for Copilot.
ms.author: camillepack
author: camillepack
manager: scotv
ms.date: 04/21/2025
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
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Microsoft 365 Copilot pay-as-you-go overview

The Microsoft 365 Copilot pay-as-you-go plan offers a flexible and cost-effective way for organizations to access Copilot services. This plan allows administrators to enable consumption-based billing for specific Copilot scenarios, providing users with the ability to use Copilot features without committing to a full license.

This article provides an overview of the pay-as-you-go plan, its benefits, and pricing details.

This article applies to:

- Microsoft 365 Copilot

## Why pay-as-you-go?

The Microsoft 365 Copilot pay-as-you-go plan offers a flexible and scalable solution for organizations looking to use AI capabilities without the commitment of a full license. By enabling consumption-based billing, administrators can better manage costs and provide users with access to powerful Copilot features as needed.

### Common use cases

- **Establish usage patterns** Understand adoption patterns for new apps to determine whether prepaid licenses make financial sense for your business.
- **Scalability** Organizations can scale their usage based on demand, paying only for the consumption.

## How does it work?

The pay-as-you-go plan allows administrators to set up billing for Microsoft 365 Copilot Chat, enabling users to access declarative agents on a consumption basis. You can manage billing, view costs, and turn off services as needed.

The following administrator roles in the Microsoft 365 admin center can view and manage pay-as-you-go:

- Global administrator
- AI administrator
- Global reader (read-only access)

## Billing process

The billing process requires two steps:

1. Add a billing policy
2. Connect billing policy to Copilot services  

### Step 1 - Add a billing policy

The billing policy acts as a distinct billing identifier that can be associated with a group responsible for the incurred cost. The main objectives of a pay-as-you-go billing policy are:

- To allocate billing responsibilities across departments
- To facilitate the reuse of billing configurations across various pay-as-you-go scenarios
- To enable administrators to enforce governance
- To link users to a policy, establishing billing rules for a group of users

#### Add or delete a billing policy

**Creating a billing policy** defines the billing infrastructure for pay-as-you-go that consists of an Azure subscription and a set of users. Creating a billing policy alone doesn't complete the billing setup. The billing policy needs to be connected to Microsoft 365 Copilot Chat to complete the setup.

**Deleting a billing policy** removes the billing infrastructure. Any connected services are disconnected from pay-as-you-go billing.

### Step 2 - Connect billing policy to Copilot services

After establishing a billing policy, the admin must link it to a Copilot service, such as Microsoft 365 Copilot Chat. This connection enables all users covered by the billing policy to access Copilot Chat.  

Admins can disconnect a billing policy when it's no longer needed for the service. Upon disconnection, users linked to that billing policy lose access to the metered agents in Copilot Chat.  

The following conditions apply when managing billing policies:

- Admin can connect or disconnect a billing policy one at a time.
- Disconnect an existing "all users" billing policy before connecting to a user-specific billing policy.

### Process for new feature releases

In the future, new features using pay-as-you-go billing will be announced via a message center post. When the features become available, users in your organization will be able to take advantage of those capabilities. Pay-as-you-go billing is disabled by default. A global admin or owner to the subscription can enable or disable Microsoft 365 pay-as-you-go features in the Microsoft 365 admin center.

## Pricing details

When you use a Microsoft Pay-as-you-go service linked to an Azure subscription, the service gets billed using the Azure subscription that you specified when you set up Pay-as-you-go billing. The Azure subscription uses the Azure meter set up for the service.

To learn more about meters, see [Meters for Microsoft 365 Copilot Chat pay-as-you-go](meters.md).

## Monitoring and billing

The organization's consumption of the pay-as-you-go service can be monitored on the [Cost Management](/microsoft-365/commerce/use-cost-mgmt) page in the Microsoft 365 admin center for each of the Microsoft 365 pay-as-you-go services that you use.

Additionally, administrators have the option to view the cost breakdown and analysis in [Microsoft Cost Management](/azure/cost-management-billing/costs/overview-cost-management) by filtering the accumulated costs using the tag with feature `m365copilotchat.`

:::image type="content" source="../media/copilot-pay-azure.png" alt-text="Screenshot showing the Cost Management page in Azure with Copilot costs.":::

## Related content

[Meters for Microsoft 365 Copilot Chat pay-as-you-go](meters.md)
