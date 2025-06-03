---
# Required metadata
# For more information, see https://learn.microsoft.com/en-us/help/platform/learn-editor-add-metadata
# For valid values of ms.service, ms.prod, and ms.topic, see https://learn.microsoft.com/en-us/help/platform/metadata-taxonomies

title:       Import or export People Skills
description: You can import skills for a user from third-party platforms and export a user’s confirmed skills using the Graph API.
author:      anibajaj 
ms.author:   anirudhbajaj
ms.service:  ms.service: microsoft-365-copilot
ms.topic:    how-to
ms.date:     05/29/2025
---

# Import or export People Skills

 You can import skills for a user from third-party platforms and export a user’s confirmed skills using the Microsoft Graph API. You can also export a user's confirmed skills.

### Importing user skills

You can import user skills from third party systems. The imported skills display on that user’s skills profile as __Imported by your organization__ and can be confirmed by a user. Once confirmed, imported skills behave the same as all confirmed skills.

 



User skills from external systems can be imported as an attribute while uploading organizational data into Microsoft 365.

Review the below guideline on how you can use the tool to import user skills:   

1.      Open the [Org. data ingestion tool ](/viva/import-orgdata)in Admin center and download the .csv template.  In admin center, see __Setup > Migration and imports__

2.      In the org. data ingestion tool template, list all the users for whom you need skills to be imported, and list each user’s skills under the attribute __Microsoft_UserSkillNames__

[See reference for org. data field in the template](/viva/orgdata-attributes)

 

3.      Make a copy of all the user skills and add them to People Skills library as custom skills. Learn more about how to add custom skills.

4.      Import the user skills data into Microsoft 365 using the .csv upload.

 

### Exporting user skills

Admins can export a user’s confirmed skills via the Profile endpoint in Microsoft Graph API. [Read our documentation ](/graph/api/profile-list-skills?view=graph-rest-beta&tabs=http)for more details on the skills endpoint and specific GET requests to access this data from the Graph API.

> [!NOTE]
> To export your entire skills library, see [exporting your entire skills library](#_Export_your_custom).  
>  Only a user’s confirmed skills can be exported. AI-generated skills can't be exported.

 

