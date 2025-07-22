---
title: Deploy the Microsoft 365 LTI App in any LTI 1.3 compliant LMS
description: Learn how to deploy the Microsoft 365 Learning Tool Interoperability (LTI) app in any LTI 1.3 compliant LMS.
author: jennplatt
ms.author: avering
manager: michal.gideoni
ms.date: 07/10/2025
audience: admin
ms.topic: how-to
ms.service: msteams
ms.subservice: teams-education
ms.collection: 
- M365-modern-desktop
- m365initiative-edu
- tier2
ms.localizationpriority: medium
---
# Deploy the Microsoft 365 LTI® app in any LTI 1.3 compliant LMS

This guide provides steps for deploying the Microsoft 365 Learning Tool Interoperability® (LTI) app in any LTI 1.3 compliant LMS.

:::image type="content" source="./media/microsoft-365-lti.png" alt-text="Screenshot of Microsoft 365 LTI." border="true":::

For an overview of the Microsoft 356 LTI integration for learning management systems (LMS), see [Integrating Microsoft products with your Learning Management System](/microsoft-365/lti/).

## Request a Microsoft 365 sandbox environment

> [!IMPORTANT]
> If you're a Microsoft Partner that has an LTI 1.3 Advantage conformant platform and wish to test deployment and functionality of the Teams Assignments LTI tool on behalf of your customers, you need a Microsoft 365 Education sandbox environment to deploy and test the application.

**To request a Microsoft 365 sandbox environment:**

1. You first need a Microsoft Partner ID. Your Microsoft Partner ID appears in the top right corner next to your name when you log into the [Microsoft Partner Center](https://partner.microsoft.com/). If you don't have one, you can obtain one by [joining the Microsoft AI Cloud Partner program](https://partner.microsoft.com/partnership).

1. When you have your Microsoft Parter ID, request a sandbox using one of the following methods based on your business type:

    - [Request a Microsoft 365 Education development/testing sandbox](https://m365edupartnerportal.powerappsportals.com/MSEDUIntegrationSignup/) as an Education ISV or SI partner who builds and supports integrations with Microsoft products and services.
    - [Request to join the Microsoft Global Training Partner program](https://m365edupartnerportal.powerappsportals.com/MSGTPSignup/) as a Training Partner who delivers training and support to customers on Microsoft products and services.

> [!IMPORTANT]
> The person who deploys this integration should be an **Administrator role in the LMS**. A person in your organization who is a **M365 Global Administrator** is also needed to help complete the configuration of the app before first time use.
>
> By installing and using the Microsoft Education LTI app, educators and students can transmit grades to the LMS where the terms of use and privacy policy of that application apply.

## LTI requirements for integration

### LTI 1.3 Advantage Complete platform implementation and conformance

The following LTI specifications should be implemented by the platform:

- [Learning Tools Interoperability (LTI) Core Specification](https://www.imsglobal.org/spec/lti/v1p3/)
- [Learning Tools Interoperability (LTI) Deep Linking Specification](https://www.imsglobal.org/spec/lti-dl/v2p0/)
- [Learning Tools Interoperability (LTI) Names and Roles Provisioning Services Specification](https://www.imsglobal.org/spec/lti-nrps/v2p0)
- [Learning Tools Interoperability (LTI) Assignment and Grading Services Specification](https://www.imsglobal.org/spec/lti-ags/v2p0)

> [!NOTE]
> [1EdTech LTI Certification](https://www.1edtech.org/certification/get-certified) isn't required but highly recommended for ensuring conformance to the above specifications.

## LMS configuration requirements for the integration

### User matching between Microsoft 365/Entra ID and the LMS

To fully integrate with your LMS environment and perform tasks on behalf of users (like populating students and co-teachers into OneNote Class Notebooks, setting file permissions, or sending grades from Assignments to the LMS gradebook), the Microsoft 365 LTI app must be able to map Student and Teacher identities between the LMS and the Microsoft Entra ID directory services. It's required to populate the LMS user Email field (which is the same email value returned from the LTI Names and Roles Provisioning Service) with the user's M365/Entra User UPN or Primary Email address. Verify this for people in every course that will use the integration to ensure the Microsoft apps can match LMS users.

## Deploy the Teams Assignments LTI® tool for your LMS

1. Go to the [Microsoft LMS Gateway](https://lti.microsoft.com/).

1. Select the **Go to Registration Portal** button.

1. Sign in with a _Microsoft 365 Education_ account (this is the account provided to you by a qualified education institution, or an account in your Edu Partner Microsoft 365 Education sandbox environment).

1. After signing in, select **Add new registration**.

1. Select **Microsoft 365 LTI**, and then select **Next**.

1. Enter an easily identifiable **Registration name**.

1. Select **Other** as the LMS platform, and then select **Next**. You're given a list of keys that need to be copied and pasted to your LMS site.

1. Leave the Microsoft LMS Gateway open in your browser tab and open the LMS site in another browser or tab and log in as an administrator.

1. Navigate to your platform's LTI 1.3 Tool configurations to add a new LTI 1.3 tool.

1. Copy the values provided and save them to the like fields in your configuration. You need to add them to your LMS LTI® 1.3 tool configuration in the following steps. Hint: Check your LMS documentation to find the steps to create a new LTI® 1.3 registration and the correct fields to paste these values into.

1. Your LMS should provide you with platform URLs that is needed to complete the Microsoft LMS Gateway registration. Hint: Check your LMS's documentation to find the correct place to get the registration values from your LMS.

1. On the Microsoft LMS gateway tab, select **LMS provided registration keys**.

1. Copy and paste the platform values from the LMS tool registration into correct fields on Microsoft's LMS provided registration keys page.

1. Select **Next**.

1. Review the fields and values summarized on the **Review and add** page.

1. If there are no errors, select **Save** and exit.

1. When you see a message indicating successful registration and summarizing the values you entered, you've completed registration of the platform on the Microsoft LMS Gateway. You can return to the Microsoft LMS Gateway to view these values for troubleshooting or to restore a registration on the LMS side anytime.

You're now ready to continue configuring common registration settings in the LTI 1.3 tool in your LMS platform.

## Configure common registration settings

Every platform may have different options and steps for completing tool registration and adding placements for where the tool is launched within the platform. However, many common settings and steps are required to successfully deploy the app.

1. Enable the tool to be available to both instructor (teacher) and learner (student) roles in the platform.

1. Enable Names and Roles Provisioning Service (NRPS).

1. Enable Assignment and Grading Services (AGS).

1. Confirm that the Name, Email, and Username of the user that launches the tool will be sent to the tool in the privacy settings.

1. Add the following custom parameters to be replaced by the platform at runtime. The LTI spec suggests the following variables be available, but platforms may have additional variables that are better suited based on definitions.

| **Name** | **LTI/LIS Variable** | **Description** | **Example expression** |
|---|---|---|---|
| **t** | ResourceLink.title | Title of the resource lineItem (assignment) from the label property | t=$ResourceLink.title |
| **dd** | ResourceLink.submission.endDateTime | Due date of the resource lineItem (assignment) from the endDateTime property | dd=$ResourceLink.submission.endDateTime |
| **mp** | N/A | Maximum score possible for a lineItem submission form the scoreMaximum property | mp=$ResourceLink.lineItem.scoreMaximum |
| **csid** | CourseOffering.sourcedId | Sourced ID for the course offering in the LMS | csid=$CourseOffering.sourcedId |
| **ssid** | CourseSection.sourcedId | Sourced IDs for the course sections in the LMS | ssid=$CourseSection.sourcedId |

1. Add the secure Icon URL from the tool values copied if the platform requires this URL to display an icon.

## Add placements for the tool to launch from in the LMS platform

The Teams Assignments LTI® tool implements several launches that can be leveraged by a platform including Resource Launches and Deep Linking launches.

- Resource Launch placement - best used in a course context as a navigation menu item placement, or where course level resources are available to instructor and student member roles.

- Deep Linking Launch placement - best used in a new assignment or content activity placement (external tool type of assignment/content) where the tool, when launched by an instructor, creates a resource link that can be launched from the assignments or content activity list by instructors and teachers. The tool also creates a lineItem and sends scores back to the LMS to sync into its gradebook as Teams Assignments are graded by the instructor.

The following table documents the launches available and their expected behaviors. Not every platform has to implement every launch.

| **Feature/Launch** | **Description** | **Role** | **LTI Launch Message Type** | **Custom claim params** | **Tool Response** | **Advantage Service Calls** | **Additional Details** | **Allowed file type** | **Pre-Viewable file types** |
|---|---|---|---|---|---|---|---|---|---|
| **M365 Navigation** | Instructors and students can navigate to all of the Microsoft Education experiences enabled in the Microsoft 365 LTI. | membership#Instructor<br>membership#Student | LtiResourceLinkRequest | N/A | Renders the OneDrive Explorer | N/A | | All File Types allowed | [As supported by OneDrive](https://support.microsoft.com/en-us/office/file-types-supported-for-previewing-files-in-onedrive-sharepoint-and-teams-e054cd0f-8ef2-4ccb-937e-26e37419c5e4) |
| **Linking OneDrive File** | An instructor can link a OneDrive File inside a course. The File is accessible as readonly to all students in the class. | membership#Instructor | LtiDeepLinkingRequest | launchType = link-selection | DeepLinkResponse with launch url<br><br>LtiLinkItem contentItem = new LtiLinkItem<br>            {<br>                Title = \<Name>,<br>                Url = \<Url>,<br>                Custom = {<br>"LtiUserId", \<LtiUserId>,<br>"Type", \<type>, // Link/Embed<br>                    "ltiContextId", \<ContextId><br>"sharedItemId", \<ItemId> // guid<br>},<br>            }; | N/A | | All File Types allowed | [As supported by OneDrive](https://support.microsoft.com/en-us/office/file-types-supported-for-previewing-files-in-onedrive-sharepoint-and-teams-e054cd0f-8ef2-4ccb-937e-26e37419c5e4) |
| **Link + embed OneDrive Files** | An instructor can link or embed a OneDrive File inside a course. The File is accessible as readonly to all students and teacher in the class. | membership#Instructor | LtiDeepLinkingRequest | launchType = shared-item | DeepLinkResponse with launch url<br>LtiLinkItem contentItem = new LtiLinkItem<br>            {<br>                Title = \<Name>,<br>                Url = \<Url>,<br>                Custom = {<br>"LtiUserId", \<LtiUserId>,<br>"Type", \<type>, // Link/Embed<br>                    "ltiContextId", \<ContextId><br>"sharedItemId", \<ItemId> // guid<br>},<br>            }; | N/A | Need mechanism to pass custom parameters in deep links https://www.imsglobal.org/spec/lti-dl/v2p0#custom-properties | All File Types allowed | [As supported by OneDrive](https://support.microsoft.com/en-us/office/file-types-supported-for-previewing-files-in-onedrive-sharepoint-and-teams-e054cd0f-8ef2-4ccb-937e-26e37419c5e4) |
| **View Linked/Embedded Files** | View the embedded files with a deep links | membership#Instructor<br>membership#Student | LtiResourceLinkRequest | | Renders the embedded file. | N/A | Custom parameters set by the deep link request must be sent in the corresponding resource link launch. | All File Types allowed | [As supported by OneDrive](https://support.microsoft.com/en-us/office/file-types-supported-for-previewing-files-in-onedrive-sharepoint-and-teams-e054cd0f-8ef2-4ccb-937e-26e37419c5e4) |
| **Create a Microsoft submittable activity that is part of an LMS content item** | An instructor adds a Microsoft document or assignment to an LMS content item (assignment) for all student members of the course to complete and submit. | membership#Instructor | LtiDeepLinkingRequest | launchType=assignments | DeepLink Response with launch url<br><br>LtiLinkItem contentItem = new LtiLinkItem<br>            {<br>                Title = \<Name>,<br>                Url = \<Url>,<br>                Custom = {<br>"LtiUserId":\<LtiUserId>,<br>"Type":\<type>, // Link/Embed<br>                    "ltiContextId":\<ContextId><br>"sharedItemId":\<ItemId> // guid,<br>"launchType":"assignments",<br>"icon: " : \<iconurl><br>},<br>            }; | N/A | Need mechanism to pass custom parameters in deep links https://www.imsglobal.org/spec/lti-dl/v2p0#custom-properties | PPTX, XLSX, DOCX | PPTX, XLSX, DOCX |
| **View a Microsoft submittable activity that is part of an LMS content item** | Students able able to view and get their own copy of the Microsoft activity (document, assignment, etc.) to view, complete, and submit | membership#Student | LtiResourceLinkRequest | launchType=assignments<br>Two additional claims required - max allowed Attempts and student attempts done | Render the assignment | N/A | - Custom parameters set by the deep link request must be sent in the corresponding resource link launch.                                                                     - The launch should have a AssignmentGradeService LineItemUrl                             - In canvas the two custom claims are <br>    "AllowedAttempts": "$Canvas.assignment.allowedAttempts",<br>    "StudentAttempts": "$Canvas.assignment.submission.studentAttempts" | PPTX, XLSX, DOCX | PPTX, XLSX, DOCX |
| **Create a microsoft submittable activity** | An instructor adds a Microsoft document or assignment to an LMS content item (assignment) for all student members of the course to complete and submit. | membership#Instructor | LtiDeepLinkingRequest | launchType=courseAssignments | DeepLink Response with launch url<br><br>LtiLinkItem contentItem = new LtiLinkItem<br>            {<br>                Title = \<Name>,<br>                Url = \<Url>,<br>                Custom = {<br>"LtiUserId":\<LtiUserId>,<br>"Type":\<type>, // Link/Embed<br>                    "ltiContextId":\<ContextId><br>"sharedItemId":\<ItemId> // guid,<br>"launchType":"assignments",<br>"icon: " : \<iconurl><br>},<br>            }; | | | | |
| **View a Microsoft submittable activity** | Students able able to view and get their own copy of the Microsoft activity (document, assignment, etc.) to view, complete, and submit. | membership#Student | LtiResourceLinkRequest | launchType=assignments<br>Two additional claims required - max allowed Attempts and student attempts done | Render the assignment | N/A | - Custom parameters set by the deep link request must be sent in the corresponding resource link launch.                                                                     - The launch should have a AssignmentGradeService LineItemUrl                             - In canvas the two custom claims are <br>    "AllowedAttempts": "$Canvas.assignment.allowedAttempts",<br>    "StudentAttempts": "$Canvas.assignment.submission.studentAttempts" | PPTX, XLSX, DOCX | PPTX, XLSX, DOCX |
| **Submit a cloud assignment** | Once students finish editing the file. OneDrive UX provides a way to submit the file which would be available to Teacher for Grading using AGS. | membership#Student | LtiResourceLinkRequest | Call is from within the OneDrive UX. | | AGS Call to upload the score.<br>LtiContentItem[] contentItems = new[]<br>                {<br>                    new LtiContentItem<br>                    {<br>                        Url = driveItemWithDownloadUrl.DownloadUrl,<br>                        Title = driveItemWithDownloadUrl.Name,<br>                        Text = driveItemWithDownloadUrl.Name,<br>                        Type = "file",<br>                    },<br>                };<br>                LtiSubmission ltiSubmission = new LtiSubmission<br>                {<br>                    SubmittedAt = DateTime.UtcNow,<br>                    ContentItems = contentItems,<br>                };<br><br>                var score = new LtiScore<br>                {<br>                    UserId = ltiUser.LtiUserId,<br>                    ActivityProgress = ActivityProgress.Completed,<br>                    GradingProgress = GradingProgess.PendingManual,<br>                    TimeStamp = DateTime.UtcNow,<br>                    Submission = ltiSubmission,<br>                };<br><br>Post Call - \<LineItemUrl>/Scores | | PPTX, XLSX, DOCX | PPTX, XLSX, DOCX |
| **Submit a Assignment using One Drive(Templateless)** | For a submission, student can upload a file using OneDrive | membership#Student | LtiDeepLinkingRequest | launchType=assignments | DeepLink response<br><br>LtiFileItem contentItem = new LtiFileItem<br>            {<br>                Title = \<name>,<br>                Url = driveItem.DownloadUrl,<br>                CopyAdvice = true,<br>                Text = \<filename>,<br>                Custom = new Dictionary<string, string><br>                {<br>                    { "LtiUserId", sharedItem.LtiUserId },<br>                    { "Type", sharedItem.ItemType },<br>                },<br>            }; | N/A | The LMS should use the downloadUrl to download the file. | All File types allowed | No preview |
| **Create a Collaboration Document** | Instructors or students can create a collaboration where all members in a course can collaborate with option to use an existing file or create a blank file. | membership#Instructor<br>membership#Student | LtiDeepLinkingRequest | launchType=collaborations | DeepLink Response with launch url<br><br>LtiLinkItem contentItem = new LtiLinkItem<br>            {<br>                Title = \<Name>,<br>                Url = \<Url>,<br>                Custom = {<br>"LtiUserId", \<LtiUserId>,<br>"Type", \<type>, // Link/Embed<br>                    "ltiContextId", \<ContextId><br>"sharedItemId", \<ItemId> // guid<br>},<br>            };<br><br>LtiDeepLinkingResponse response = new LtiDeepLinkingResponse<br>            {<br>                Data = ltiDeepLinkingRequest?.DeepLinkingSettings?.Data,<br>                DeploymentId = ltiDeepLinkingRequest?.DeploymentId,<br>ContentItem = {<br>Title = collaborationFileRequest.DocumentName,<br>Url = documentLink,<br>Text = collaborationFileRequest.DocumentDescription,<br>Type = "ltiResourceLink",<br>Custom = new Dictionary<string, string>()<br>{<br>{ "launchType", "collaborations" },<br>{ "sharedItemId", sharedItem.ItemId },<br>},<br>"https://canvas.instructure.com/lti/collaboration" = {<br>Users = [],<br>Groups = []<br>}<br><br>}<br>}<br>            }; | NRPS | 1. Max 250 members allowed in collaboration.<br>2. | PPTX, XLSX, DOCX | PPTX, XLSX, DOCX |
| **View a Collaboration Document - Jatin** | Opening a collaboration document | membership#Instructor<br>membership#Student | LtiResourceLinkRequest | launchType = collaborations<br>sharedItemId = \<itemId> | Renders the collaboration document | | | PPTX, XLSX, DOCX | PPTX, XLSX, DOCX |
| **Copy Assignments from One Course to another** | Copy assignments that contain OneDrive LTI resources; allows educators to import existing assignments to new courses | membership#Instructor<br>membership#Student | LtiResourceLinkRequest | **ContextHistory=$Context.id.history** (irrespective of placement; as in canvas) | Copies over the resource and renders it when launched | | Prerequisite: Context.id.history LTI parameter must be implemented http://www.imsglobal.org/spec/lti/v1p3/#lti-context-variable | | |
| **Admin settings UX launch** | | System/person#Administrator<br>Institution/person#Administrator | LtiResourceLinkRequest | launchType=account | Renders admin settings UX | | | | |

<details>
<summary>### M365 Navigation</summary>

#### Feature/Launch
M365 Navigation

#### Description
Instructors and students can navigate to all of the Microsoft Education experiences enabled in the Microsoft 365 LTI.

#### Role
membership#Instructor  
membership#Student

#### LTI Launch Message Type
LtiResourceLinkRequest

#### Custom claim params
N/A

#### Tool Response
Renders the OneDrive Explorer

#### Advantage Service Calls
N/A

#### Additional Details

#### Allowed file type
All File Types allowed

#### Pre-Viewable file types
[As supported by OneDrive](https://support.microsoft.com/en-us/office/file-types-supported-for-previewing-files-in-onedrive-sharepoint-and-teams-e054cd0f-8ef2-4ccb-937e-26e37419c5e4)
</details>

<details>
<summary>### Linking OneDrive File</summary>

#### Feature/Launch
Linking OneDrive File

#### Description
An instructor can link a OneDrive File inside a course. The File is accessible as readonly to all students in the class.

#### Role
membership#Instructor

#### LTI Launch Message Type
LtiDeepLinkingRequest

#### Custom claim params
launchType = link-selection

#### Tool Response
DeepLinkResponse with launch url

LtiLinkItem contentItem = new LtiLinkItem  
{  
&nbsp;&nbsp;Title = \<Name>,  
&nbsp;&nbsp;Url = \<Url>,  
&nbsp;&nbsp;Custom = {  
&nbsp;&nbsp;&nbsp;&nbsp;"LtiUserId", \<LtiUserId>,  
&nbsp;&nbsp;&nbsp;&nbsp;"Type", \<type>, // Link/Embed  
&nbsp;&nbsp;&nbsp;&nbsp;"ltiContextId", \<ContextId>  
&nbsp;&nbsp;&nbsp;&nbsp;"sharedItemId", \<ItemId> // guid  
&nbsp;&nbsp;}  
};

#### Advantage Service Calls
N/A

#### Additional Details

#### Allowed file type
All File Types allowed

#### Pre-Viewable file types
[As supported by OneDrive](https://support.microsoft.com/en-us/office/file-types-supported-for-previewing-files-in-onedrive-sharepoint-and-teams-e054cd0f-8ef2-4ccb-937e-26e37419c5e4)
</details>

<details>
<summary>### Link + embed OneDrive Files</summary>

#### Feature/Launch
Link + embed OneDrive Files

#### Description
An instructor can link or embed a OneDrive File inside a course. The File is accessible as readonly to all students and teacher in the class.

#### Role
membership#Instructor

#### LTI Launch Message Type
LtiDeepLinkingRequest

#### Custom claim params
launchType = shared-item

#### Tool Response
DeepLinkResponse with launch url

LtiLinkItem contentItem = new LtiLinkItem  
{  
&nbsp;&nbsp;Title = \<Name>,  
&nbsp;&nbsp;Url = \<Url>,  
&nbsp;&nbsp;Custom = {  
&nbsp;&nbsp;&nbsp;&nbsp;"LtiUserId", \<LtiUserId>,  
&nbsp;&nbsp;&nbsp;&nbsp;"Type", \<type>, // Link/Embed  
&nbsp;&nbsp;&nbsp;&nbsp;"ltiContextId", \<ContextId>  
&nbsp;&nbsp;&nbsp;&nbsp;"sharedItemId", \<ItemId> // guid  
&nbsp;&nbsp;}  
};

#### Advantage Service Calls
N/A

#### Additional Details
Need mechanism to pass custom parameters in deep links https://www.imsglobal.org/spec/lti-dl/v2p0#custom-properties

#### Allowed file type
All File Types allowed

#### Pre-Viewable file types
[As supported by OneDrive](https://support.microsoft.com/en-us/office/file-types-supported-for-previewing-files-in-onedrive-sharepoint-and-teams-e054cd0f-8ef2-4ccb-937e-26e37419c5e4)
</details>

<details>
<summary>### View Linked/Embedded Files</summary>

#### Feature/Launch
View Linked/Embedded Files

#### Description
View the embedded files with a deep links

#### Role
membership#Instructor  
membership#Student

#### LTI Launch Message Type
LtiResourceLinkRequest

#### Custom claim params

#### Tool Response
Renders the embedded file.

#### Advantage Service Calls
N/A

#### Additional Details
Custom parameters set by the deep link request must be sent in the corresponding resource link launch.

#### Allowed file type
All File Types allowed

#### Pre-Viewable file types
[As supported by OneDrive](https://support.microsoft.com/en-us/office/file-types-supported-for-previewing-files-in-onedrive-sharepoint-and-teams-e054cd0f-8ef2-4ccb-937e-26e37419c5e4)
</details>

<details>
<summary>### Create a Microsoft submittable activity that is part of an LMS content item</summary>

#### Feature/Launch
Create a Microsoft submittable activity that is part of an LMS content item

#### Description
An instructor adds a Microsoft document or assignment to an LMS content item (assignment) for all student members of the course to complete and submit.

#### Role
membership#Instructor

#### LTI Launch Message Type
LtiDeepLinkingRequest

#### Custom claim params
launchType=assignments

#### Tool Response
DeepLink Response with launch url

LtiLinkItem contentItem = new LtiLinkItem  
{  
&nbsp;&nbsp;Title = \<Name>,  
&nbsp;&nbsp;Url = \<Url>,  
&nbsp;&nbsp;Custom = {  
&nbsp;&nbsp;&nbsp;&nbsp;"LtiUserId":\<LtiUserId>,  
&nbsp;&nbsp;&nbsp;&nbsp;"Type":\<type>, // Link/Embed  
&nbsp;&nbsp;&nbsp;&nbsp;"ltiContextId":\<ContextId>  
&nbsp;&nbsp;&nbsp;&nbsp;"sharedItemId":\<ItemId> // guid,  
&nbsp;&nbsp;&nbsp;&nbsp;"launchType":"assignments",  
&nbsp;&nbsp;&nbsp;&nbsp;"icon: " : \<iconurl>  
&nbsp;&nbsp;}  
};

#### Advantage Service Calls
N/A

#### Additional Details
Need mechanism to pass custom parameters in deep links https://www.imsglobal.org/spec/lti-dl/v2p0#custom-properties

#### Allowed file type
PPTX, XLSX, DOCX

#### Pre-Viewable file types
PPTX, XLSX, DOCX
</details>

<details>
<summary>### View a Microsoft submittable activity that is part of an LMS content item</summary>

#### Feature/Launch
View a Microsoft submittable activity that is part of an LMS content item

#### Description
Students able able to view and get their own copy of the Microsoft activity (document, assignment, etc.) to view, complete, and submit

#### Role
membership#Student

#### LTI Launch Message Type
LtiResourceLinkRequest

#### Custom claim params
launchType=assignments  
Two additional claims required - max allowed Attempts and student attempts done

#### Tool Response
Render the assignment

#### Advantage Service Calls
N/A

#### Additional Details
- Custom parameters set by the deep link request must be sent in the corresponding resource link launch.  
- The launch should have a AssignmentGradeService LineItemUrl  
- In canvas the two custom claims are  
&nbsp;&nbsp;"AllowedAttempts": "$Canvas.assignment.allowedAttempts",  
&nbsp;&nbsp;"StudentAttempts": "$Canvas.assignment.submission.studentAttempts"

#### Allowed file type
PPTX, XLSX, DOCX

#### Pre-Viewable file types
PPTX, XLSX, DOCX
</details>

<details>
<summary>### Create a microsoft submittable activity</summary>

#### Feature/Launch
Create a microsoft submittable activity

#### Description
An instructor adds a Microsoft document or assignment to an LMS content item (assignment) for all student members of the course to complete and submit.

#### Role
membership#Instructor

#### LTI Launch Message Type
LtiDeepLinkingRequest

#### Custom claim params
launchType=courseAssignments

#### Tool Response
DeepLink Response with launch url

LtiLinkItem contentItem = new LtiLinkItem  
{  
&nbsp;&nbsp;Title = \<Name>,  
&nbsp;&nbsp;Url = \<Url>,  
&nbsp;&nbsp;Custom = {  
&nbsp;&nbsp;&nbsp;&nbsp;"LtiUserId":\<LtiUserId>,  
&nbsp;&nbsp;&nbsp;&nbsp;"Type":\<type>, // Link/Embed  
&nbsp;&nbsp;&nbsp;&nbsp;"ltiContextId":\<ContextId>  
&nbsp;&nbsp;&nbsp;&nbsp;"sharedItemId":\<ItemId> // guid,  
&nbsp;&nbsp;&nbsp;&nbsp;"launchType":"assignments",  
&nbsp;&nbsp;&nbsp;&nbsp;"icon: " : \<iconurl>  
&nbsp;&nbsp;}  
};

#### Advantage Service Calls

#### Additional Details

#### Allowed file type

#### Pre-Viewable file types

</details>

<details>
<summary>### View a Microsoft submittable activity</summary>

#### Feature/Launch
View a Microsoft submittable activity

#### Description
Students able able to view and get their own copy of the Microsoft activity (document, assignment, etc.) to view, complete, and submit.

#### Role
membership#Student

#### LTI Launch Message Type
LtiResourceLinkRequest

#### Custom claim params
launchType=assignments  
Two additional claims required - max allowed Attempts and student attempts done

#### Tool Response
Render the assignment

#### Advantage Service Calls
N/A

#### Additional Details
- Custom parameters set by the deep link request must be sent in the corresponding resource link launch.  
- The launch should have a AssignmentGradeService LineItemUrl  
- In canvas the two custom claims are  
&nbsp;&nbsp;"AllowedAttempts": "$Canvas.assignment.allowedAttempts",  
&nbsp;&nbsp;"StudentAttempts": "$Canvas.assignment.submission.studentAttempts"

#### Allowed file type
PPTX, XLSX, DOCX

#### Pre-Viewable file types
PPTX, XLSX, DOCX
</details>

<details>
<summary>### Submit a cloud assignment</summary>

#### Feature/Launch
Submit a cloud assignment

#### Description
Once students finish editing the file. OneDrive UX provides a way to submit the file which would be available to Teacher for Grading using AGS.

#### Role
membership#Student

#### LTI Launch Message Type
LtiResourceLinkRequest

#### Custom claim params
Call is from within the OneDrive UX.

#### Tool Response

#### Advantage Service Calls
AGS Call to upload the score.

LtiContentItem[] contentItems = new[]  
{  
&nbsp;&nbsp;new LtiContentItem  
&nbsp;&nbsp;{  
&nbsp;&nbsp;&nbsp;&nbsp;Url = driveItemWithDownloadUrl.DownloadUrl,  
&nbsp;&nbsp;&nbsp;&nbsp;Title = driveItemWithDownloadUrl.Name,  
&nbsp;&nbsp;&nbsp;&nbsp;Text = driveItemWithDownloadUrl.Name,  
&nbsp;&nbsp;&nbsp;&nbsp;Type = "file",  
&nbsp;&nbsp;}  
};  
LtiSubmission ltiSubmission = new LtiSubmission  
{  
&nbsp;&nbsp;SubmittedAt = DateTime.UtcNow,  
&nbsp;&nbsp;ContentItems = contentItems,  
};  

var score = new LtiScore  
{  
&nbsp;&nbsp;UserId = ltiUser.LtiUserId,  
&nbsp;&nbsp;ActivityProgress = ActivityProgress.Completed,  
&nbsp;&nbsp;GradingProgress = GradingProgess.PendingManual,  
&nbsp;&nbsp;TimeStamp = DateTime.UtcNow,  
&nbsp;&nbsp;Submission = ltiSubmission,  
};  

Post Call - \<LineItemUrl>/Scores

#### Additional Details

#### Allowed file type
PPTX, XLSX, DOCX

#### Pre-Viewable file types
PPTX, XLSX, DOCX
</details>

<details>
<summary>### Submit a Assignment using One Drive(Templateless)</summary>

#### Feature/Launch
Submit a Assignment using One Drive(Templateless)

#### Description
For a submission, student can upload a file using OneDrive

#### Role
membership#Student

#### LTI Launch Message Type
LtiDeepLinkingRequest

#### Custom claim params
launchType=assignments

#### Tool Response
DeepLink response

LtiFileItem contentItem = new LtiFileItem  
{  
&nbsp;&nbsp;Title = \<name>,  
&nbsp;&nbsp;Url = driveItem.DownloadUrl,  
&nbsp;&nbsp;CopyAdvice = true,  
&nbsp;&nbsp;Text = \<filename>,  
&nbsp;&nbsp;Custom = new Dictionary<string, string>  
&nbsp;&nbsp;{  
&nbsp;&nbsp;&nbsp;&nbsp;{ "LtiUserId", sharedItem.LtiUserId },  
&nbsp;&nbsp;&nbsp;&nbsp;{ "Type", sharedItem.ItemType },  
&nbsp;&nbsp;}  
};

#### Advantage Service Calls
N/A

#### Additional Details
The LMS should use the downloadUrl to download the file.

#### Allowed file type
All File types allowed

#### Pre-Viewable file types
No preview
</details>

<details>
<summary>### Create a Collaboration Document</summary>

#### Feature/Launch
Create a Collaboration Document

#### Description
Instructors or students can create a collaboration where all members in a course can collaborate with option to use an existing file or create a blank file.

#### Role
membership#Instructor  
membership#Student

#### LTI Launch Message Type
LtiDeepLinkingRequest

#### Custom claim params
launchType=collaborations

#### Tool Response
DeepLink Response with launch url

LtiLinkItem contentItem = new LtiLinkItem  
{  
&nbsp;&nbsp;Title = \<Name>,  
&nbsp;&nbsp;Url = \<Url>,  
&nbsp;&nbsp;Custom = {  
&nbsp;&nbsp;&nbsp;&nbsp;"LtiUserId", \<LtiUserId>,  
&nbsp;&nbsp;&nbsp;&nbsp;"Type", \<type>, // Link/Embed  
&nbsp;&nbsp;&nbsp;&nbsp;"ltiContextId", \<ContextId>  
&nbsp;&nbsp;&nbsp;&nbsp;"sharedItemId", \<ItemId> // guid  
&nbsp;&nbsp;}  
};  

LtiDeepLinkingResponse response = new LtiDeepLinkingResponse  
{  
&nbsp;&nbsp;Data = ltiDeepLinkingRequest?.DeepLinkingSettings?.Data,  
&nbsp;&nbsp;DeploymentId = ltiDeepLinkingRequest?.DeploymentId,  
&nbsp;&nbsp;ContentItem = {  
&nbsp;&nbsp;&nbsp;&nbsp;Title = collaborationFileRequest.DocumentName,  
&nbsp;&nbsp;&nbsp;&nbsp;Url = documentLink,  
&nbsp;&nbsp;&nbsp;&nbsp;Text = collaborationFileRequest.DocumentDescription,  
&nbsp;&nbsp;&nbsp;&nbsp;Type = "ltiResourceLink",  
&nbsp;&nbsp;&nbsp;&nbsp;Custom = new Dictionary<string, string>()  
&nbsp;&nbsp;&nbsp;&nbsp;{  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ "launchType", "collaborations" },  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ "sharedItemId", sharedItem.ItemId },  
&nbsp;&nbsp;&nbsp;&nbsp;},  
&nbsp;&nbsp;&nbsp;&nbsp;"https://canvas.instructure.com/lti/collaboration" = {  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Users = [],  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Groups = []  
&nbsp;&nbsp;&nbsp;&nbsp;}  
&nbsp;&nbsp;}  
};

#### Advantage Service Calls
NRPS

#### Additional Details
1. Max 250 members allowed in collaboration.

#### Allowed file type
PPTX, XLSX, DOCX

#### Pre-Viewable file types
PPTX, XLSX, DOCX
</details>

<details>
<summary>### View a Collaboration Document - Jatin</summary>

#### Feature/Launch
View a Collaboration Document - Jatin

#### Description
Opening a collaboration document

#### Role
membership#Instructor  
membership#Student

#### LTI Launch Message Type
LtiResourceLinkRequest

#### Custom claim params
launchType = collaborations  
sharedItemId = \<itemId>

#### Tool Response
Renders the collaboration document

#### Advantage Service Calls

#### Additional Details

#### Allowed file type
PPTX, XLSX, DOCX

#### Pre-Viewable file types
PPTX, XLSX, DOCX
</details>

<details>
<summary>### Copy Assignments from One Course to another</summary>

#### Feature/Launch
Copy Assignments from One Course to another

#### Description
Copy assignments that contain OneDrive LTI resources; allows educators to import existing assignments to new courses

#### Role
membership#Instructor  
membership#Student

#### LTI Launch Message Type
LtiResourceLinkRequest

#### Custom claim params
**ContextHistory=$Context.id.history** (irrespective of placement; as in canvas)

#### Tool Response
Copies over the resource and renders it when launched

#### Advantage Service Calls

#### Additional Details
Prerequisite: Context.id.history LTI parameter must be implemented http://www.imsglobal.org/spec/lti/v1p3/#lti-context-variable

#### Allowed file type

#### Pre-Viewable file types

</details>

<details>
<summary>### Admin settings UX launch</summary>

#### Feature/Launch
Admin settings UX launch

#### Description

#### Role
System/person#Administrator  
Institution/person#Administrator

#### LTI Launch Message Type
LtiResourceLinkRequest

#### Custom claim params
launchType=account

#### Tool Response
Renders admin settings UX

#### Advantage Service Calls

#### Additional Details

#### Allowed file type

#### Pre-Viewable file types

</details>

## First-time Configuration by an LMS Administrator

You must launch the app for the first time as a user with an **LMS** **Administrator** role (http://purl.imsglobal.org/vocab/lis/v2/system/person#Administrator or http://purl.imsglobal.org/vocab/lis/v2/institution/person#Administrator) to complete the configuration for your deployment and activate the tool. Users won't have access until you complete this step.

1. As an LMS Administrator, access any course that has the tool deployed with a Resource or DeepLinking launch.

2. Launch the tool to trigger the Admin Settings first-run experience for configuration.

3. Continue with the [**Microsoft 365 LTI first-time configuration steps**](microsoft-365-lti-first-time-configuration.md) to complete the configuration for your organization.

The Microsoft Education app is deployed, configured, and is ready to use in your LMS!

## Ongoing use by educators and students in a course

On first access, users must sign in using their Microsoft 365 (Microsoft Entra) account.

## Browser settings

- Cookies should be allowed for Microsoft apps.

- Popups shouldn't be blocked for Microsoft apps.

If you receive an error message regarding cookies being blocked, check your browser's address bar for an icon to allow third-party cookies and popups. If this issue persists, review your settings related to cookies and popups to make sure they're allowed for this app.

## Getting help and giving feedback

- LMS and Microsoft 365 admins can contact Microsoft [Education Support](https://aka.ms/edusupport) to help resolve configuration and deployment issues, for themselves or on behalf of users.

- Educators and Learners can contact support or give feedback directly from the app through the help and feedback menu.

:::image type="content" source="./media/help-and-feedback.png" alt-text="Screenshot of link to send feedback for Microsoft 365 LTI." border="true":::

Learning Tools Interoperability® (LTI®) is a trademark of the 1EdTech Consortium, Inc. (**[**1edtech.org**](https://1edtech.org)**).
