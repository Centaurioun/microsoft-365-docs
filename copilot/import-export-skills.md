---
# Required metadata
# For more information, see https://learn.microsoft.com/en-us/help/platform/learn-editor-add-metadata
# For valid values of ms.service, ms.prod, and ms.topic, see https://learn.microsoft.com/en-us/help/platform/metadata-taxonomies

title:       # Add a title for the browser tab
description: # Add a meaningful description for search results
author:      anibajaj # GitHub alias
ms.author:   anirudhbajaj # Microsoft alias
ms.service:  # Add the ms.service or ms.prod value
# ms.prod:   # To use ms.prod, uncomment it and delete ms.service
ms.topic:    # Add the ms.topic value
ms.date:     05/29/2025
---

# Import or export skills

 You can import skills for a user from third-party platforms and export a user’s confirmed skills using the Graph API.



### Importing user skills

You can import user skills from third party systems. The imported skills display on that user’s skills profile as __Imported by your organization__ and can be confirmed by a user. Once confirmed, imported skills behave the same as all confirmed skills.

 



User skills from external systems can be imported as an attribute while uploading organizational data into Microsoft 365. <u>Please review the detailed instructions about how to upload your org. data here.</u>

Review the below guideline on how you can use the tool to import user skills:   

1.      Open the [Org. data ingestion tool ](/viva/import-orgdata)in Admin center and download the .csv template.  In admin center, you will find this under __Setup > Migration and imports__

2.      In the org. data ingestion tool template, list all the users for whom you need skills to be imported, and list each user’s skills under the attribute __Microsoft_UserSkillNames__

[See reference for org. data field in the template](/viva/orgdata-attributes)

 

3.      Make a copy of all the user skills and add them to People Skills library as custom skills. Learn more about how to add custom skills.

4.      Import the user skills data into Microsoft 365 using the .csv upload.

 

### Exporting user skills

Admins can export a user’s confirmed skills via the Profile endpoint in MS Graph API.  <ins>Read our [profile list skills] documentation for https://learn.microsoft.com/en-us/graph/api/profile-list-skills?view=graph-rest-beta&tabs=http </ins>more details on the skills endpoint and specific GET requests to access this data from the Graph API.

Learn about [exporting your entire skills library](#_Export_your_custom).  

 __Note__

Only a user’s confirmed skills can be exported. AI-suggested skills cannot be exported.

 

---
 [[SK1]](#_msoanchor_1)[@Anirudh Bajaj](mailto:anirudhbajaj@microsoft.com) presumably this should be a link?
