---
title:       # Manage custom skills
description: # Manage custom skills and import and export settings. 
author:      anibajaj 
ms.author:   anirudhbajaj
ms.service:  ms.service: microsoft-365-copilot
ms.topic:    how-to
ms.date:     05/29/2025
---

# Manage custom skills

If you didn't import custom skills as a part of your initial setup, you can add it later by following the guide below. You can also delete or export custom skills.

> [!NOTE]
> Importing custom skills is optional and is intended for mature customers. You can use People Skills if you’ve selected skills from the out-of-the-box library.

### View your custom skills (if custom skills were set up during initial setup)

1.      Under __Skills,__ select __People Skills Library,__ and then select __Custom skills__. You can filter by role and search by skill name.

2.      Select __View details__ to see an overview of your imported files, who completed the import, and the import date.

### Import custom skills library

Follow these steps to either import your custom skills library for the first time or to reimport with changes to your initial custom import.

> [!NOTE]
>  Subsequent imports of a custom skills library overwrite existing data. New skills will be added to your library. Deleted skills and any data associated with those skills will be deleted. Any updates to skill name or skill description will reflect in the user's experience.
> Permissions are required to view and edit the uploaded .csv files in SharePoint.

To import customs skills into Skills:

1. Under __Skills,__ select the __Import custom skills__ tab

2.      Select __Download library template__ and __Download mapping template.__

3.      Open the template files you downloaded. Follow the steps in [Create the custom skills files](/viva/skills/skills-get-started) to create your skills library and skills mapping files.

4.      Paste the file paths for both files into the __Skills library file path__ and __Skill mapping file path__ fields.

5.      Select __Next__ to begin file validation. If there's a problem with the file, you see an error message at this step.

 

> [!NOTE]
> You need permissions to view and edit the uploaded .csv files in SharePoint to import custom skills information.
> If you see a "file not found" error, try deleting "%20" strings from your pasted file paths.

6.      Review your custom skills data.

- The number of skills from the out-of-the-box library.

- The number of skills and number of roles/job titles from your custom import.

- The number of duplicate skills identified in your selection. If you have duplicates, your organization's custom data is prioritized over data from the out-of-the-box library.

7.    Acknowledge that importing custom skills will immediately impact your users' experience if skills is turned on.

8.      Select __Confirm__ to import.



### Export your custom skills library

You can export the custom skills that you've set up in your skills library.

1.      Under __Skills,__ select __Export library__.

2.      Select __Export custom skills__ to export your custom skills import files.

 



### Delete custom skills

Deleting custom skills immediately removes all of these skills from user experiences and deletes all data associated with those skills.

1.      Under __Skills,__ select __People Skills Library__, and then select __Custom skills__.

2.      Select __Delete custom skills__.

3.      Select __Delete__ to confirm that you want to delete your custom skills.

 



