---
title: Known issues and limitations for the Employee Self-Service agent
f1.keywords: NOCSH
ms.author: daisyfeller
author: daisyfell
manager: triciagill
ms.date: 7/3/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.custom: ess-agent
robots: NOINDEX, NOFOLLOW
ms.localizationpriority: medium
ms.collection: m365copilot
description: Learn about the known issues and limitations affecting the Employee Self-Service agent and the workarounds you can employ.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Known issues and limitations for the Employee Self-Service agent

>[!NOTE]
>The Employee Self-Service agent is currently in preview. Deployment processes are subject to change before this product becomes generally available.

The following known issues and limitations affect the Employee Self-Service (ESS) agent.

- The ESS Agent is currently only available in English. More languages will be available after the agent reaches general availabality.
- The ESS Agent currently doesn’t support on-premises data gateways, even if only used for authentication.
- The following file size limits apply to knowledge sources. For files exceeding the size limits, consider alternative architectures such as [Microsoft 365 Semantic Indexing](/microsoftsearch/semantic-index-for-copilot) or [connecting your data to Azure OpenAI for Generative answers.](/microsoft-copilot-studio/nlu-generative-answers-azure-openai)
  - SharePoint sources for users with no Copilot license: up to 7 MB
  - SharePoint sources for users with a Copilot license: Up to 200 MB
  - Files uploaded as a knowledge source: Up to 512 MB
- Pages with multiple links that lead to the relevant information aren't included in the generative answers. Consider adding relevant information for each link in a page that has multiple links.
- Customizations aren’t stored automatically in the preferred solution for exporting and importing to different environments.
- Agent names have length constraints of 42 characters maximum. Names exceeding this limit cause erroneous rendering.
- The ESS agent isn't fully tested and validated for third-party identity providers.
- The ESS agent isn't fully tested and validated for third-party hosted single sign-on (SSO).

## Troubleshooting

If publishing takes more than 48 hours, you can use the manual manifest upload option in Integrated Apps. [Learn how to use the manual manifest upload]()