---
title: Agent installation in Microsoft 365 Copilot
f1.keywords:
ms.author: erikre
author: ErikRe
manager: dansimp
ms.date: 06/18/2025
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- m365copilot
- magic-ai-copilot
description: Learn about deployment and governance methods for agents in Microsoft 365 Copilot.
---

# Agent installation in Microsoft 365 Copilot

Microsoft 365 Copilot can be extended by installing agents. [Agents](/microsoft-365-copilot/extensibility/agents-overview) provide additional knowledge, skills, and automated workflows to address your unique business needs and enhance workflows within Microsoft 365 Copilot. In addition, Microsoft 365 Copilot can deliver highly skilled expertise on demand.

Two featured agents that are used with Microsoft 365 Copilot are Microsoft's Researcher and Analyst agents. These agents are AI-powered productivity tools that enhance workflows within Microsoft 365 Copilot. Individual users can share and unpin these agents. In addition, these agents, as well as non-Microsoft agents, help you analyze vast amounts of information with secure, compliant access to your work data. 

> [!NOTE]
> Microsoft deployed the Researcher and Analyst agents to existing users with Microsoft 365 Copilot licenses.

There are different methods used to install agents in Microsoft 365 Copilot.

## Agent installation and governance methods

Microsoft 365 Copilot currently provides the following deployment and governance methods for agents:
- [Microsoft-installed agents and features](#microsoft-installed-agents-and-features)
- [Admin-installed agents](#admin-installed-agents)
- [User-installed agents](#user-installed-agents)

### Microsoft-installed agents and features

Microsoft may install a small number of agents and features that augment Microsoft 365 Copilot with highly valuable skills. These agents and features, built by Microsoft, are preinstalled and/or pre-pinned in Microsoft 365 Copilot for all licensed users. Currently, only the Researcher and Analyst agents are deployed this way.

Organizations can govern these agents in the Copilot Control System section of the Microsoft 365 admin center. There, administrators can block these agents in their tenant, making them inaccessible to all users. Granular controls allowing assignment of these agents to specific users and groups are therefore grayed-out. Alternately, administrators can [disable or restrict Copilot extensibility](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps) for their organization, however this will apply to all agents, not just Microsoft-deployed agents. Individual users can share and unpin these agents as well.

### Admin-installed agents

Administrators can install their own custom-built, Microsoft-built, or partner-built agents to augment Microsoft 365 Copilot. Administrators can install a limited number of agents to the Copilot rail or make them available to users through the [Agent Store in Microsoft 365 Copilot](https://devblogs.microsoft.com/microsoft365dev/introducing-the-agent-store-build-publish-and-discover-agents-in-microsoft-365-copilot/).

Organizations can govern these agents in the Copilot Control System section of the Microsoft 365 admin center. Administrators have a full set of lifecycle management tools for these apps. Microsoft offers granular controls that enable administrators to install, block, and remove these agents for some or all of the users in their tenant. 

> [!NOTE]
> Admins can only remove shared agents and custom LOB agents.

For more information, see [Manage agents for Microsoft 365 Copilot in the Microsoft 365 admin center](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps).

### User-installed agents

Users can install agents that are available in Agent Store based on the policies set by their tenant administrators. Users can also install their own custom-built agents. For example, these custom-built agents could be built with Agent Builder, SharePoint or Microsoft Copilot Studio, to augment Microsoft 365 Copilot. These agents are used by individuals, and optionally shareable within the user’s organization.

Organizations can govern these agents in the Copilot Control System section of the Microsoft 365 admin center. Administrators have a full set of lifecycle management tools for these apps. Microsoft offers granular controls that enable administrators to install and block agents. Additionally, administrators can remove shared and custom agents for some or all of the users in their tenant.

## Related content

- [Manage agents for Microsoft 365 Copilot in the Microsoft 365 admin center](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps)
- [Agent Store in Microsoft 365 Copilot](https://devblogs.microsoft.com/microsoft365dev/introducing-the-agent-store-build-publish-and-discover-agents-in-microsoft-365-copilot/)
- [Agents for Microsoft 365 Copilot](/microsoft-365-copilot/extensibility/agents-overview)
- [Build agents with Copilot Studio agent builder](/microsoft-365-copilot/extensibility/copilot-studio-agent-builder-build)
- [Copilot Studio overview](/microsoft-copilot-studio/fundamentals-what-is-copilot-studio)
