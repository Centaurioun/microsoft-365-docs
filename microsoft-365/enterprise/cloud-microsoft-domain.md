---
title: "Unified cloud.microsoft domain for Microsoft 365 apps"
description: Describes the new cloud.microsoft domain for Microsoft 365 apps
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 04/09/2025
ms.topic: overview
ms.service: microsoft-365-enterprise
ms.subservice: network
ms.localizationpriority: medium
ms.collection: must-keep
ms.custom: QuickDraft
ms.reviewer: dansimp
search.appverid: MET150
f1.keywords:
audience:
content_well_notification:
- AI-contribution
---

# Unified cloud.microsoft domain for Microsoft 365 apps

Microsoft is unifying user-facing Microsoft 365 apps and services to a single and consistent domain: `cloud.microsoft`.

The growth of Microsoft cloud services led to the expansion of the domain space they occupy, resulting in [hundreds of domains](https://aka.ms/m365endpoints). This fragmentation is a challenge for end user navigation, administrative simplicity, and the development of cross-app experiences. To solve this problem and to make it easier for customers, end users and app developers to interface with Microsoft 365 apps and services, Microsoft has designated a special domain - `cloud.microsoft`, to be used by Microsoft SaaS products going forward.     

The `.microsoft` top-level domain is exclusive to Microsoft. The new domain doesn’t have traditional suffixes such as `.com` or `.net` in the end. This is by design. `cloud.microsoft` resides under the `.microsoft` top-level domain, for which Microsoft is a registry operator and the sole registrant. This domain allows for extra security, privacy, and protection against spoofing when you interact with apps within that domain. You can trust that any website or app that ends with `cloud.microsoft` is an official Microsoft product or service.

Some Microsoft 365 products that are already using the `cloud.microsoft` domain include Microsoft 365 Copilot Chat, Word, Excel, PowerPoint, Outlook, OneNote, Planner, Microsoft Loop, Mesh, Viva Engage, Viva Insights, Viva Learning, Viva Pulse, and more. These are just some examples, and over time you will see even more Microsoft 365 product experiences to be delivered from the `cloud.microsoft` domain.

## Benefits of a unified domain

Consolidating authenticated user-facing Microsoft 365 experiences to a single domain benefits customer in several ways. For end users, it streamlines the overall experience by reducing sign-ins, redirects, and delays when navigating across apps. For admins, it reduces the complexity of allowlists that are required to connect to Microsoft 365 services and help your organization stay secure and productive. For all our customers – and our developers – this change helps align for better and tighter integration across the Microsoft 365 ecosystem by streamlining development and improving performance of cross-app experiences.

'Dot brand' top-level domains like `.microsoft` enhance security, trustworthiness, and integrity. Microsoft has exclusive rights to the `.microsoft` top-level domain, enabling enhanced security protocols and governance controls to be applied across the entire domain hierarchy, starting from the top level. All experiences on the `.microsoft` domain are guaranteed to be legitimate and authentic, as Microsoft is the registry operator and sole registrant.

## Security considerations

To ensure that customers and users can treat everything under the `*.cloud.microsoft` domain as fully trusted, the entire domain hierarchy is isolated, purpose built, and dedicated to hosting only secure and compliant Microsoft product experiences. The domain is managed to the highest standards of domain security and reputation, and is kept free of scenarios such as third-party websites, IaaS/PaaS resources (such as file and blob storage), and hosting of active content, code, or scripts that might affect the trust and integrity of products and applications residing in the domain.

The `.microsoft` gTLD (Generic Top-Level Domain) is on the HTTP Strict-Transport-Security preload list in all popular browsers, meaning that all nonsecure HTTP requests are automatically upgraded to use HTTPS, and users are blocked from overriding certificate errors that could indicate an active network attacker is attempting to compromise the security of the connection. All `*.cloud.microsoft` subdomains inherit this protection.

## Requirements for admins

Since 2023, `*.cloud.microsoft` and other domains related to the domain unification initiative are part of the [Microsoft 365 network guidance on domains and service endpoints](/microsoft-365/enterprise/urls-and-ip-address-ranges). Customers who use the Microsoft 365 web service API to automate network settings have been getting the network settings since then. Customers who manually update endpoints should ensure that `*.cloud.microsoft` and other required domains are included in their allowlist to prevent connectivity and service incidents for their users. 

## See also

- [Introducing cloud.microsoft: a unified domain for Microsoft 365 apps and services](https://techcommunity.microsoft.com/t5/microsoft-365-blog/introducing-cloud-microsoft-a-unified-domain-for-microsoft-365/ba-p/3804961)
- [Office 365 URLs and IP address ranges](/microsoft-365/enterprise/urls-and-ip-address-ranges)
