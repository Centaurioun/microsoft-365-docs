---
# Required metadata
# For more information, see https://learn.microsoft.com/en-us/help/platform/learn-editor-add-metadata
# For valid values of ms.service, ms.prod, and ms.topic, see https://learn.microsoft.com/en-us/help/platform/metadata-taxonomies

title:       Set up People Skills
description: how you can set up People Skills for the first time in your organization
author:      anibajaj 
ms.author:   anirudhbajaj 
ms.service: microsoft-365-copilot
ms.topic:    how-to
ms.date:     05/29/2025
---

# Set up People Skills

This section walks though how you can set up People Skills for the first time in your organization. After initial set up is complete, admins can edit their skill library or sharing settings through the steps in the [Manage your skills library](people-skills-manage-skills-library.md) page.

## Admin roles required for setup

The following roles have permission to set up People Skills. Review the documentation for [assigning roles](/entra/identity/role-based-access-control/manage-roles-portal)

- AI administrator
- Knowledge Administrator

## Quick setup with out-of-the-box skill library

Most organizations can quickly set up skills using our out-of-the-box People Skills library of over 16,000+ skills. If you prefer to curate your own library by importing custom skills, please see the next section [Advanced setup](#Advanced-setup-using-a-custom-skills-library).

1. In the Copilot page in the [Microsoft 365 admin center](https://admin.microsoft.com/adminportal/home#/featureexplorer), select **People Skills in Microsoft 365 Copilot** 

   > [!NOTE]
   > You can also find People Skills under _Settings_, then _Viva_, under the **Data Management** tab
   
   
1. Select _Being quick setup_

1. Choose the skills you want to use from the out-of-the-box library.

The more skills you include from the default library, the more specific AI-generated skills will be for users. All skills in the library, including all 16,000 skills, are pre-selected by default

- If you want to remove skills from your library, you can select _View and edit People Skills_

- You may add or remove skills later after setting up People Skills. Learn how to [Manage your skills library](people-skills-manage-skills-library.md).

4. You can choose whether to **share skill data with Viva Insights** (Recommended). People Skills in Viva Insights allows organizations and leaders to discover skills within their workforce and assess skill distribution across groups. Learn more about the [skills landscape report in Viva Insights](/viva/insights/advanced/introduction-to-advanced-insights).

This selection can be updated later from People Skills settings. 



5.      Hit **Confirm** to finish quick setup.

People Skills initial AI-inferences should start showing up for users within 48 hours and may take up to 5 days to complete for all users in your tenant.

You can change the settings confirmed during this setup [by Managing your skills library](people-skills-manage-skills-library.md) in the settings page.  

Learn more about [sharing controls](people-skills-sharing-inferencing-controls.md) to manage which skills are shared across your organization.

## Advanced setup using a custom skills library

Organizations can build their own custom skills library with a combination of skills from the out-of-the-box skills library and by importing your own custom skills.

1. In the Copilot page in the [Microsoft 365 admin center](https://admin.microsoft.com/adminportal/home#/featureexplorer), select People Skills in Microsoft 365 Copilot

1. > [!NOTE]
> You can also find People Skills under _Settings_, then _Viva_, under the _Data Management_ tab

2. Under _Custom Setup_, select _Begin custom setup_   

3.  To use a custom skills library, download the template files. Select _Download library template_ and _Download mapping template_.

(This step is optional if you are only using skills from the out-of-the-box People Skills library. Select _Next_ to skip this step.)

TBD-Screenshot

4.      Fill out the templates as described in [Create the custom skills files](/viva/skills/skills-get-started) to create the library and mapping files and then get the paths to those completed files.

- Paste the file paths for both files into the _Skills library file path_ and _Skill mapping file path_ fields. 

- Select _Next_ to begin file validation. 

- If there's a problem with the file, you see an error message at this step.

5.      Review your organization’s skills library details

- The number of skills from the out-of-the-box library. Note: You can select which skills you want to include from our default library of 16,000 skills by clicking “Edit People Skills”. You can also do this later after the initial setup, see [Manage your skills library](people-skills-manage-skills-library.md)

-  The number of skills and number of roles/job titles from your custom import.

- The number of duplicate skills identified in your selection. If you have duplicates, your organization's custom data is prioritized over data from the out-of-the-box library.

TBD-Screenshot

6.        Select _Turn on People Skills in Viva Insights_, if it's available for your tenant. Skills in Viva Insights allows organizations and leaders to discover skills within their workforce and assess skill distribution across groups. Learn more about the [skills landscape report in Viva Insights](/viva/insights/advanced/introduction-to-advanced-insights). 

7. If everything looks correct, select _Confirm_ .

 

8.      Review People Skills Settings:

You can disable skill AI inferencing or set default skill sharing for specific users, groups, or your entire tenant by using an access control policy. Configure these settings through People Skills settings. For more information, see [Manage which skills are shared and use of skills AI inferencing](people-skills-ai-inferencing.md).

9.       Review your skills library and settings information. If there are any changes you want to make, go back to those steps and edit.

When you're ready, select _Done_.

Your skills library is created, and your settings are saved. Initial AI-inferences display to users within 48 hours for up to a maximum of 5 days. You can change the setting confirmed during this setup [by Managing your skills library](people-skills-manage-skills-library.md) in the settings page. 

Learn more about [sharing controls](people-skills-sharing-inferencing-controls.md) to manage which skills are shared across your organization.

### Create custom skills files

To import custom skills into your skills library, create a file that lists those custom skills and their descriptions. Optionally, you can also create a file that maps skills to specific jobs in your organization.

Before you get started, review the following information:

- You need a minimum of 20 skills to import custom skills.

- Each file must be under 100 mb.

- The following characters can't be used as a prefix in any imported field '+', '-', '@', '=', '\t', '\r'

- Save your template files as .csv (comma separated) files, with no spaces in the file name.

- Make sure you use commas as the delimiter. Your system might default to a different delimiter. In European countries, for example, it's often set to a semicolon.

To create your custom skills files:

1.      Open the template files you downloaded during People Skills setup.

2.      Enter the skills for your custom skills library into the library template.

-  Required fields: _Skill ID (externalCode)_, _Skill Name (Name.en_US)_

-  Recommended fields: _Skill Description (Description.en_US)_

-  Optional field: _Restricted Skill tag_ (mark Yes or No)



See example input below, replicate this for each custom skill in your file:

|Skill ID|SN0001|
| -------- | -------- |
|_Skill ID_|SN0001|
|_Skill Name_|Customer Insights|
|_Skill Description_|The ability to understand customer needs and validate that their needs are being met.|
|_Restricted Skill_|Yes|

[Learn more about restricted skills](people-skills-manage-ai-restricted-skills.md)

4.      Save the templates as .csv files in a secure SharePoint location.

5.      Get the file paths for your .csv files.

a.      Select the file, and then select the ellipsis (_..._).

b.     Select _Details_, and then scroll to find the _Path_.

c.      Select the option to copy the selected file's path to the Clipboard. The file path should be formatted like this: *https://contoso.sharepoint.com/TeamAdmin/Shared%20Documents/Skills_Library.csv*

### Create Role to skill mapping file (Optional)

Admins can upload a file to map your custom skills to specific roles or jobs in your organization.

Before you get started, review the following information:

- _Skill ID (externalCode)_ in the library file must map to _Skill ID (SkillExternalCode)_ in the role to skill mapping file.

- The following characters can't be used as a prefix in any imported field '+', '-', '@', '=', '\t', '\r'

- Save your template files as .csv (comma separated) files, with no spaces in the file name.

- Make sure you use commas as the delimiter. Your system might default to a different separator. In European countries, for example, it's often set to a semicolon “;”

To create your role to skill mapping file:

1.      Open the template file you downloaded during People Skills setup.

2.      Enter the role and skills information into the library template.

-  Required fields: _Job Title_, _Skill ID (externalCode)_ 

- Recommended fields: _Skill Name (Name.en_US)_

See example input below, replicate this for each custom skill in your file:

|Job Title|Software Engineer II|
| -------- | -------- |
|_Job Title_|Software Engineer II|
|_Skill ID_|SN0001|
|_Skill Name_|Cloud Security|

 
4.      Save the templates as .csv files in a secure SharePoint location.

5.      Get the file paths for your .csv files.

f.        Select the file, and then select the ellipsis (_..._).

g.      Select _Details_, and then scroll to find the _Path_.

h.      Select the option to copy the selected file's path to the Clipboard. The file path should be formatted like this: *https://contoso.sharepoint.com/TeamAdmin/Shared%20Documents/Skill_Mapping.csv*

