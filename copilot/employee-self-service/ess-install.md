---
title: Install the Employee Self-Service agent
f1.keywords: NOCSH
ms.author: daisyfeller
author: daisyfell
manager: triciagill
ms.date: 6/20/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.custom: ess-agent
ms.localizationpriority: medium
ms.collection: m365copilot
description: Learn about the installation stage in the deployment process for the Employee Self-Service agent.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Install the Employee Self-Service agent

After completing the required steps in the [preparation](ess-prepare.md) stage, you can install the Employee Self-Service (ESS) agent in a specific Power Platform environment.

## Activities summary

|Role |Activities to perform |Configuration area |
|-----|----------------------|-------------------|
|Environment administrator |- Select the right environment </br>- Set up a preferred solution </br>- Install the ESS agent |Microsoft Copilot Studio |

## Select the right environment

1. Sign in to [Microsoft Copilot Studio](https://copilotstudio.microsoft.com) as an assigned Environment Administrator.
1. Before installing the agent, make sure that the correct Power Platform environment is selected by verifying the name in the ribbon.

## Set up a preferred solution

1. Set up a preferred solution before performing any customizations, as the default solution contains all the core components of Dataverse, which cannot be exported or imported into another environment.
1. Based on the application lifecycle management guidelines, create a new unmanaged solution in the Dev. environment so the customizations can be performed and exported as managed solution to a Test/UAT/PROD environment.
1. Select **Solutions** in the left navigation pane.
1. Select **+New solution** and fill in the required information.
1. Provide publisher information. Make sure to provide the prefix value, which is used to create objects for this solution prefixed with the given string. For example, if your prefix is "contoso," a new object might be named "contoso_Object".
1. Select **Create** to finish creating the solution.
1. Select **Back to solutions** in the left navigation pane.