---
title: Responsible AI FAQ for the Employee Self-Service agent
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
description: Learn how the Employee Self-Service agent uses AI.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Responsible AI FAQ for the Employee Self-Service agent

>[!NOTE]
>The Employee Self-Service agent is currently in limited public preview. Deployment processes are subject to change before this product becomes generally available.

## What is Employee Self-Service? 

Employee Self-Service Agent (ESS) is a new set of capabilities to answer policy related questions and simplify HR and IT related tasks for faster resolution helping to improve the employee experience. The agent makes it easy for employees to: 

## Retrieve the right information at the right time 

Take actions on essential HR and IT tasks-in line without navigating to multiple tools and workspaces, including help and running diagnostics on Microsoft 365 products and services 

And while the ESS Agent will be ready to go day one, IT/admins will further customize the agent with OOB preconfigured no-code templates for key workflows, and connectors to third-party HR/IT systems in Copilot Studio for faster Time-To-Value (TTV). 

## What can Employee Self-Service do?  

Employee Self-Service Agent (ESS) within Microsoft 365 Copilot streamlines HR and IT tasks, providing faster resolutions and a more intuitive user experience. Key capabilities include retrieving and taking actions on HR & IT related tasks like benefits, starting a leave of absence, getting assistance for Microsoft 365 products, creating/retrieving/updating IT tickets. These features empower employees to efficiently manage their tasks, enhancing their overall experience and productivity 

## What are Employee Self-Service’s intended uses? 

Employee Self-Service (ESS) is designed to streamline and expedite various HR and IT tasks, providing faster resolutions and a more intuitive user experience. Its primary uses include retrieving and taking actions on HR and IT related queries, providing quick personalized responses to employee questions, ensuring confidentiality in conversations, and allowing employees to provide feedback to help shape the agent for Microsoft and its customers 

## How was Employee Self-Service evaluated? What metrics are used to measure performance? 

ESS provides a topic out-of-box, which is disabled by default. This topic tries to identify queries related to discrimination, harassment, abuse, unethical behavior, retaliation and other sensitive issues, and responds with a predetermined response, ensuring that LLM doesn't generate incorrect information for such queries. Your organization can define your own predetermined verbatim responses, update the topic as required, or disable the topic as required. 

Employee Self-Service (ESS) is evaluated with manual red teaming with prompts customized for the scenarios. Microsoft evaluated more than 200 prompts for discrimination, harassment, abuse, and other sensitive use cases with zero defects identified (with default ESS configuration and enabling the sensitive topic). 

## What are the limitations of Employee Self-Service? How can users minimize the impact of Employee Self-Service’s limitations when using the system? 

ESS relies on Microsoft Copilot Studio for processing of user queries. Microsoft Copilot Studio limitations inherently apply for Employee Self-Service as well. Refer to the Copilot Studio documentation for the protections in place for responsible AI - FAQ for generative answers - Microsoft Copilot Studio | Microsoft Learn 

## What operational factors and settings allow for effective and responsible use of Employee Self-Service? 

Employee Self-Service (ESS) provides authoritative responses based on the knowledge sources added and the ISV packages configured. To provide users with authoritative responses, add appropriate knowledge sources and/or configure ISV packages.  

## How do I provide feedback on Employee Self-Service? 

To provide feedback on the Employee Self-Service (ESS) Agent, you can use the thumbs up/thumbs down buttons at the bottom of your Microsoft 365 Copilot results. 

## Does the data retrieved from 3P ISVs pass through Copilot RAI? 

If the ISV data is returned directly - such as inserting values like employee numbers into predefined templates without modification - it bypasses Copilot RAI. However, if the data is processed using a large language model (LLM) to generate a summarized or narrative response, such as explaining the meaning of a specific policy along with its value, then it goes through the summarization node, which triggers Copilot RAI. This approach is also used for content like knowledge base articles, where the system may either return the article as-is or synthesize a concise summary using LLMs. In short, Copilot RAI is engaged only when LLM-based summarization or transformation of ISV data is involved.

## What are plugins and how does Employee Self-Service use them?   

Employee Self-Service provides out-of-box topics and ISV packages (HR and IT connectors in the customize tab) to be used as per your business requirements. These topics can be customized as per your requirements, and you can also add your own topics. 

## What data can Employee Self-Service provide to plugins? What permissions do Employee Self-Service plugins have?  

Employee Self-Service doesn't provide any specific data till the point Power Platform admin configured knowledge source and/or ISV packages. For adding SharePoint as Knowledge source, SharePoint permissions apply by default. For ISV package, it depends on the permissions granted by the tenant and the permissions the users have for the ISV tools. 

## What kinds of issues may arise when using Employee Self-Service enabled with plugins?   

Connection failures to connected knowledge source or ISV package may lead to access error respectively. To mitigate such errors, connection to knowledge source or ISV package needs to be verified and corrected. 