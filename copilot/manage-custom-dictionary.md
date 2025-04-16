---
title: "Manage a Custom Dictionary for Copilot"
ms.author: fezuo
author: fei.zuo
ms.reviewer: camillepack
manager: scotv
ms.date: 4/16/2025
audience: Admin
ms.topic: concept-article
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- scotvorg
- m365copilot
- magic-ai-copilot
description: Learn about how to upload and manage a Copilot Custom Dictionary.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Upload and manage a Custom Dictionary

This article provides a guide on enhancing the accuracy of Teams Transcription entity recognition and consequently improving the quality of Copilot in Teams and Recap by uploading a Custom Dictionary via the Microsoft 365 admin center.

> [!NOTE]  
> This article is intended for IT administrators. The Custom Dictionary is designed to be effective at the tenant level. If you are an end user, please contact your IT administrator for assistance.

## Custom Dictionary eligibility

The Custom Dictionary is available for Microsoft Entra account users with Copilot or Teams Premium licenses. If your Tenant admin has uploaded the dictionary and you are the meeting organizer or initiator who starts the transcription, the Custom Dictionary will be applied to improve the recognition of all entities throughout the meeting.

## Why do I need a Custom Dictionary?

Organizations often utilize unique terminologies, acronyms, and jargon, including product names, department-specific language, and industry-specific terms. The precise recognition and transcription of these terms are crucial, particularly during Teams meetings and in the AI-driven summaries and recaps provided by Copilot.

The AI models powering Teams Transcription are trained using general datasets and might not recognize these specialized terms. However, by importing a Custom Dictionary, the model can dynamically adapt during meetings and perform post correction after the meeting, leading to a significant improvement in the transcription accuracy of these specialized terms.

## What is included in a Custom Dictionary

The Custom Dictionary is designed to capture tenant-specific terminology. Leveraging technological innovations, the dictionary features a user-friendly format with simplified content to enhance the AI model's understanding of entities.

### Dictionary Content

The dictionary is presented in a flat list format, with optional fields for recording the "sounds like form” and "spell out form", as well as a comments section to provide additional context. This assists IT administrators in managing and collecting entries from internal systems or product groups effectively. Each Custom Dictionary includes the following columns:

| Term | Sounds like Form | Spell Out Form | Description |
|:-----|:-----|:-----|:-----|
|The display form of the term or phrase. This field is required to validate an entry.| A column to record how the word was pronounced in a meeting. This field is optional. |A column to clarify potential acronyms or abbreviations. This field is optional. |A column to provide additional context or full meaning of the term. This field is optional.|

### Dictionary sample

The following are examples of dictionary entries. The first column, **Term**, is the most important and should be mapped to your expected format from the transcription output.

| Term | Sounds like Form | Spell Out Form | Description |
|:-----|:-----|:-----|:-----|
|TAC| Tee-Ay-Cee| Teams Admin Center| Admin portal managing Teams|
|TAT| Tee-Ay-Tee| Turn Around time| Metrics used to applied by support team|
|Viva Glint| Vee-Vah-Glint | |  Part of Microsoft Viva|

> [!TIP]
> The **Term** column is mandatory, while all other columns are optional.

### Dictionary file format and language

The dictionary should be compiled in a CSV plain-text format with UTF-8 encoding and comma-delimited format. It is recommended to use the Excel output format option “CSV UTF-8 (comma delimited)”. Each dictionary can contain up to 500 terms/entries. Administrators can upload one dictionary per language, which will be applied to the target Teams Transcription language(region) setting as mapped below.

| Custom Dictionary Language | Teams Transcription Language |
|:-----|:-----|
|English|English (United States)|
|English  |English (United Kingdom)
|English  |English (Australia)
|English  |English (Canada)
|English  |English (India)
|Spanish  |Spanish (Spain)
|Spanish  |Spanish (Mexico)
|Japanese  |Japanese (Japan)
|French  |French (France)
|French  |French (Canada)
|German  |German (Germany)
|Portuguese  |Portuguese (Brazil)
|Italian  |Italian (Italy)
|Chinese(Simplified) |Chinese (Simplified, China)

## Step-by-step instructions

### Navigate through the Microsoft 365 admin center

1. Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).
2. From the left navigation panel, select **Copilot**, and go to the **Settings**.
3. Select **Copilot Custom Dictionary** and click on it to see the flyout view from the right for Custom Dictionary management.
4. Click **Upload Dictionary** to go to the uploading sub view

> [!TIP]
> Admins need to have Global Admin or AI Admin permissions to perform this action. To learn more about these roles, see [About admin roles in the Microsoft 365 admin center](/microsoft-365/admin/add-users/about-admin-roles)

### Create the Custom Dictionary with a CSV file

5. Select the option to download the **CSV template with header only** from the portal.
6. Open the template with Excel, open with UTF-8 and comma-delimited format.
7. Fill in your custom terms in the **Term** column as a flat list.
8. (optional) Fill in additional information in the **Sounds like form**, **Spell Out Form**, and **Description** columns.
9. Save the file as CSV UTF-8 (Comma delimited) (.csv).

### Uploading the Custom Dictionary

10. Return to the uploading view and select your CSV file in the **Upload CSV file with terms** field.
11. Select the target language for this dictionary, then click **Upload**.

> [!NOTE]  
> Ensure that the language selection matches the intended language for transcription.

12. After the loading page, a message will appear at the top of the view indicating if the upload was successful. If successful, your dictionary will appear in the dictionary list in the management view.
13. Wait for up to 24 hours for the dictionary to become effective in Teams Transcription, applicable to all meetings from your tenant.

## Optimizing your Custom Dictionary

• Include Key Terminology: Add terminology, acronyms, and entity names that are frequently mentioned in your meetings, especially those related to your important products and teams.

• Allowed Symbols in Term: Please do not include punctuation in "Term" column and use less symbols. Symbols allowed in the middle of terms are: **-'/&·ㆍ**.

• Localize Dictionaries: Collect custom terms from each local group to create dictionaries in the corresponding languages. For example, in the Japanese dictionary, some terms may remain in their English Latin form, while others may have local variants. Include all these terms in the Japanese Custom Dictionary to benefit meetings where Japanese is the primary language.

• Break Down Multi-Word Names: For names with multiple words, consider splitting them into individual parts. For instance, instead of "Copilot in Power Platform and Dynamics 365," create separate entries for "Copilot," "Power Platform," and "Dynamics 365."

• Utilize Copilot for Additional Fields: Use Copilot to generate entries for "Sounds like form," "Spell Out Form," and "Description," then review and modify them as needed.

• Avoid Short Words: It is not recommended to include very short term like "AB."

• Avoid Numeric Terms: Avoid including terms that are purely numeric like "123".

• Avoid Repeated Chars Only: Avoid using terms with repeated chars only, such as "AAA".

## Frequently asked questions

### Can I update the custom dictionary after it has been uploaded?

Yes, IT administrators can update the Custom Dictionary with new terms and product names. Uploading a new dictionary will replace the existing one in the same language.

### How does the custom dictionary affect the Teams transcription quality?

The custom dictionary is used for dynamic adaptation in meeting transcriptions. It improves the accuracy of tenant-specific terms, ensuring they are correctly transcribed during Teams meetings. This also benefits downstream AI services that rely on the transcription.

### Can end users add their custom terms directly to the dictionary?

No, end users cannot directly add terms to the dictionary. They need to ask their IT administrators to upload an updated dictionary with the new internal terms.

### Is my uploaded custom dictionary safely stored and anyone can access it?

Uploaded custom dictionary is safely stored. Only tenant user and IT administrators can access it.

### Is my uploaded custom dictionary data being added in into the model ?

No, the custom dictionary data will be used solely within the tenant for the user's meetings. It is treated as "eyes-off" data, meaning it will not be accessed by anyone or included in model training.

## Related articles

• Improving Teams Meeting Transcriptions
• Managing Custom Dictionaries in Microsoft 365
• Enhancing Copilot Performance with Custom Data
