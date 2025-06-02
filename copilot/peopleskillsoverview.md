---
# Required metadata
# For more information, see https://learn.microsoft.com/en-us/help/platform/learn-editor-add-metadata
# For valid values of ms.service, ms.prod, and ms.topic, see https://learn.microsoft.com/en-us/help/platform/metadata-taxonomies

title:       Overview of People Skills
description: People Skills is an AI-powered service that creates personalized skill profiles for users, integrating with Microsoft 365 tools to enhance skills-based experiences.
author:      anibajaj 
ms.author:   anirudhbajaj
ms.service:  ms.service: microsoft-365-copilot
ms.topic:    overview
ms.date:     05/29/2025
---

# Overview of People Skills

> [!NOTE]
> This feature is currently in preview. Preview features or services are in development, may not be available to all customers, and are made available on a "preview" basis so you can get early access and send us feedback.

People Skills is an AI-driven service that uses state-of-the-art AI to generate personalized skill profiles for your users mapped to a customizable, built-in taxonomy. This service provides a data layer that fuels the Skills agent, and enhances Microsoft 365 Copilot, Microsoft 365, and Viva services with contextualized data and skills-driven experiences.   

People Skills:

- Equips leaders with critical workforce skill insights to prepare and accelerate their AI transformation.

- Empowers employees with personalized skill profiles and experiences to help them connect with others and discover opportunities.

[Learn more about how skills AI inferencing works.](/editor/MicrosoftDocs/microsoft-365-docs-pr/copilot%2Fpeopleskillsoverview.md/pr/28574/docs-editor%2Fpeopleskillsoverview-1748550104?branch=main)

## Licensing

People Skills comes with your Microsoft 365 Copilot or Viva licenses and doesn't need a separate license. People Skills AI inferencing and experiences are based on a user's Microsoft 365 Copilot, Microsoft 365, Office 365, and Viva plans.

- __People Skills - Foundation service plan__: Customers with the “People Skills – Foundation" service plan (Microsoft 365 commercial customers without a Microsoft 365 Copilot SKU, excluding education and government) will have access to the People Skills service excluding AI inferencing and Microsoft 365 Copilot capabilities. Users with this service plan can search to add skills from your taxonomy or imported skills to create a skills profile using the Microsoft 365 profile editor.

- __People Skills – Advanced service plan__: Customers with the “People Skills – Advanced" service plan (including Microsoft Viva Suite, Viva Insights (including Workplace Analytics and Feedback customers), and Viva Learning customers) will have access to the People Skills service with AI inferencing, excluding Microsoft 365 Copilot capabilities.

- __Microsoft 365 Copilot in Productivity Apps service plan__: Customers with the “Microsoft 365 Copilot in Productivity Apps service plan,” excluding education and government SKUs, will now have People Skills available, including AI-inferencing and related Copilot experiences.

For a detailed list of People Skills experiences and their corresponding license requirements, please see below.

![People Skills 101](https://review.learn.microsoft.com/en-us/editor/MicrosoftDocs/microsoft-365-docs-pr/copilot%2Fpeopleskillsoverview.md/pr/28574/media/peopleskillsoverview/people-skills-101.png)

Contact your Microsoft representative if you have questions on licensing or access.

## Where does People Skills data appear?

- **[Skills in the Microsoft 365 profile card](https://support.microsoft.com/en-us/office/overview-of-people-skills-988029ce-f749-4f99-a6f3-f2e4cef450ae)**[:](https://support.microsoft.com/en-us/office/overview-of-people-skills-988029ce-f749-4f99-a6f3-f2e4cef450ae) Users can view and manage their skills profiles right from the Microsoft 365 profile card and profile editor. All users can also view the shared skills of others in the organization on their profile card, to help facilitate connection.

People Skills is available today on the profile card in the new Outlook desktop for Windows, Outlook Web App, Microsoft 365 Copilot, Office.com, SharePoint, and People Companion, and will expand to additional applications where you see the profile card in future releases.



- **[Skills in Microsoft 365 Copilot](https://support.microsoft.com/en-us/office/overview-of-people-skills-988029ce-f749-4f99-a6f3-f2e4cef450ae)**[:](https://support.microsoft.com/en-us/office/overview-of-people-skills-988029ce-f749-4f99-a6f3-f2e4cef450ae) If you use Microsoft 365 Copilot, shared skills surface in people related queries in Copilot to help form connections and find people with the skills you need.

- **Skills in Org Explorer and People Companion**: Tools like [Org Explorer](https://support.microsoft.com/en-us/topic/org-explorer-40c65909-b12d-4ab9-8d6c-a1592789dc8e) and [People Companion](/microsoft-365-apps/companions/people) help users quickly find the right person for a given need based on their shared skills data.

- **Skills in Viva Learning:** Users can manage skills they want to grow within Viva Learning and receive personalized course recommendations based on those skills.

- **[Skills in Copilot Analytics](/viva/insights/advanced/analyst/templates/skills-landscape)**[ (Viva Insights)](/viva/insights/advanced/analyst/templates/skills-landscape): The Skills landscape report allows organizational analysts to discover top skills in their workforce, assess their distribution across groups, identify potential gaps, and explore related skill insights.

- **Skills for Leaders in Microsoft 365 Copilot** (coming soon): Copilot enables leaders to ask targeted or broad questions about their team’s skills and receive instant, data-driven answers.

- **Skills Agent** (coming soon): The Skills agent helps employees and leaders explore, manage, and use organizational skills for personal growth and strategic planning.

People Skills AI inferencing and experiences are based on a user's Microsoft 365 Copilot, Microsoft 365, Office 365, and Viva plans. Read more about [licensing in People Skills](/editor/MicrosoftDocs/microsoft-365-docs-pr/copilot%2Fpeopleskillsoverview.md/pr/28574/docs-editor%2Fpeopleskillsoverview-1748550104?branch=main).

## Sharing and management of skills data

Users can now manage and share their skills directly from the profile card in Microsoft 365. [Learn more about People Skills capabilities for users](https://go.microsoft.com/fwlink/?linkid=2313228)

Admins can view [Set up Skills](/viva/skills/skills-get-started) and [Manage your skills library](/viva/skills/manage-skills-library) for information about how to setup People Skills, and control how People Skills data is shared and managed.

 



## User Profile Application (UPA) Skills

If your organization depends on skills data that appears in About Me on the Microsoft 365 profile card and editor (formerly in Delve), or on the skills field in the UPA API or Graph API, those skills are hidden from the Microsoft 365 profile card and editor when you deploy People Skills and replaced with this new experience.

People Skills will migrate shared UPA user skills data to the new profile card Skills experience at a future date.

When you deploy People Skills, skills from these other sources continue to be accessible to your users to edit. They can edit using the SharePoint user profile editor and will continue to surface in some experiences, such as Microsoft 365 Copilot chat and people search.

 

If you have an existing dependency on UPA skills or other solutions for ingesting skills into Microsoft 365 experiences, [please let us know using this form](https://go.microsoft.com/fwlink/?linkid=2320998). We will to follow-up with you to understand your requirements and discuss options.

