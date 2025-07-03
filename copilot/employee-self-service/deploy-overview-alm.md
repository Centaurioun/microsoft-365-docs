---
title: Employee Self-Service agent deployment overview
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
description: Learn about the deployment process and application lifecycle management for the Employee Self-Service agent
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Employee Self-Service agent deployment overview

>[!NOTE]
>The Employee Self-Service agent is currently in on-demand preview. Deployment processes are subject to change before this product becomes generally available.

There are several steps necessary to deploy the Employee Self-Service (ESS) Agent. Refer to the table for an overview of the deployment process.

|Role |Development environment |Production environment |
|-----|------------------------|-----------------------|
|Power Platform administrator |- Create environment for development and testing.</br> - Create a preferred custom solution. |Create an environment for production rollout. |
|Copilot Studio maker |- Install the ESS agent.</br> - Install ISV extension packs and set up connectors.</br> - Customize and test.</br> - Export as a managed solution. |-Install the ESS agent.</br> - Import customization solution.</br> - Test.</br> - Publish. |

## Development stages

There are four stages in developing the ESS agent.

1. Prepare:
    1. Set up roles.
    1. Set up your environment.
    1. Infra, set up for third-party ISV integration.
2. Install:
    1. Install the ESS agent.
    1. Install third-party ISV packages.
3. Customize:
    1. Configure core ESS agent.
    1. Provide third-party ISV configurations.
    1. Identify knowledge sources.
    1. Provide frequent queries.
    1. Identify sensitive queries.
4. Publish:
    1. Publish ESS agent.
    1. Approve ESS agent.
    1. Identify test users.

## Determine your application lifecycle management process

Application lifecycle management (ALM) includes governance, development, and maintenance. The key areas of ALM are as follows:

**Governance** includes managing requirements, managing resources, nurturing and system administration such as data security, user access, change tracking, reviewing, auditing, deployment control, and rollback.

**Application development** includes identifying current issues, planning, design, building and testing the application, and making continuous improvements. This area includes traditional developer and app maker roles.

**Maintenance** includes deploying the app and maintaining optional and dependent technologies.

The application lifecycle is the cyclical software development process that involves these areas: plan and track, develop, build and test, deploy, operate, monitor, and learn from discovery.
ALM for Microsoft Copilot Studio uses Dataverse in Microsoft Power Platform to securely store and manage the data and processes that business applications use. To use the Power Platform features and tools available to manage ALM, all environments that participate in ALM must include a Dataverse database.

The following concepts are important for understanding ALM using Microsoft Power Platform:

**Solutions** are the mechanisms for implementing ALM. You use solutions to distribute components across environments through export and import. A component represents an artifact used in your application that you can potentially customize. Anything that can be included in a solution is a component, such as tables, columns, canvas and model-driven apps, Power Automate flows, agents, charts, and plugins.

**Dataverse** stores all the artifacts, including solutions and [in-product deployment pipelines](/power-platform/alm/pipelines).

**Source control** is your source of truth for storing and collaborating on your components. [Learn more about source control](/power-platform/alm/git-integration/overview).

**Continuous integration and continuous delivery platforms** such as [Azure DevOps](/azure/devops/user-guide/what-is-azure-devops?view=azure-devops&preserve-view=true) allows you to automate your build, test, and deployment pipeline. These platforms can also be used with in-product pipelines.

Every organization has their own ALM process to deploy and test enterprise applications. The ESS Agent is published using Microsoft Copilot Studio, which brings Power Platform ALM directly into the Copilot Studio app.
Makers and developers work in development environments using unmanaged solutions, then import them to other downstream environments, such as tests, as managed solutions.
You need to work with your organization’s Power Platform administrator to establish your ALM process. It’s recommended to have at least two separate environments to author, update, and test the agent.

The ESS Agent has three distinct persona experiences:

1. Administrator: Prepare the tenant to deploy, configure, and operate the ESS agent with the correct roles assigned to identified service owners.

2. Environment maker: Install, configure, and publish the agent, including third-party ISV packages.

3. User: Consume the ESS Agent within Microsoft Teams or Microsoft 365 Copilot chat. Users’ data is harnessed from Microsoft 365 Graph.

These experiences are within the boundary of a single tenant, whereas the environment maker’s experience installing and publishing the agent can vary among different environments within Power Platform. It’s therefore recommended to establish ALM environments such as Developer, Test, and Production for publishing and testing the ESS Agent. Each of the third-party ISV applications can also be connected to the respective environments if each application has their own ALM instances (such as Developer, Test, and Production).
It's recommended to have end users using a live production tenant to make use of recent and meaningful user-object interactions in Microsoft Graph.
