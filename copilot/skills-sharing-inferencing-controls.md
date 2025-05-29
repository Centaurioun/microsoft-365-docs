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

# Manage privacy and sharing controls

As an admin, you can set privacy and skill sharing controls for users, groups, or the entire tenant to meet your organization's needs and comply with local or business requirements. These settings can also be used to selectively deploy People Skills to a small group of pilot users, while restricting functionality to the rest of your tenant.

People Skills provides access controls using <u>Feature Access Management</u>.

## Overview of controls offered

Navigate to the People Skills setup page and select __Settings__ to view your skills sharing and privacy settings. 

These access controls can be created before, during or after People Skills setup. 

#### Skills AI inferencing control overview

This setting controls whether users receive AI-generated skills relevant to their role.

AI inferencing is enabled by default, but you can let users opt in or out or disable inferencing entirely during People Skills setup.

Options available:

- Admins can turn skills inferencing auto-on. Individual users can opt out.

- Admins can turn skills inferencing auto-off. Individual users can opt in. 

- Admins can disable skills inferencing for their tenant.

####  Skills visibility controls overview 

Skills visibility controls whether users can see their colleagues’ skills on Microsoft 365 surfaces like the people card or in Copilot.

 All skills in a user's profile are shared and visible by default once you set up People Skills in your tenant. You can also change these visibility controls before or after setting up People Skills.

 

Options available:

·         Admins can turn skills visibility auto-on. Individual users can opt out.

·         Admins can turn skills visibility auto-off. Individual users can opt in.

·         Admins can disable skills visibility of *some* skills (AI-generated or imported skills) for their tenant. 

 

We offer three levels of controls to control skill visibility. Each of these can be enabled or disabled as per the options above using their own access policy.   

- __(Parent control) Visibility of entire skills profile:__ An individual's skills profile consists of AI-generated skills, user-confirmed skills, and imported skills (if applicable). If sharing is disabled, all user skills will be private and not shared in any user, leader, or organizational analyst experiences.

- __(Child control) Visibility of AI-generated skills:__ AI-generated skills are skills based on AI inferencing that are relevant to a user’s role. These skills can only be shown if the skills profile (parent) is also set to visible. This is a separate control for both admins and for users to manage sharing of these skills, even if the user’s profile is set to visible.

- __(Child control)__ __Visibility of imported skills:__ User skills from third-party applications may be imported by your organization. Because we are unable to know if they were previously confirmed by users, they are shown in experiences as skills a user might have until the user confirms them, much like AI-generated skills. These skills can only be shown if the skills profile (parent) is also set to visible. This is a separate control for both admins and for users to manage sharing of these skills, even if the user’s profile is set to visible.

The following sections walk-through how-to setup each of the controls in detail, and expected functionality when they are enabled or disabled.

## Manage skills data sharing with Viva Insights

When checked, skills data is passed on to Viva Insights. Skills in Insights allows organizations and leaders to discover skills within their workforce and assess skill distribution across groups. Learn more about People Skills in Viva Insights.

You can stop skills data from being shared with Viva Insights by unchecking this setting.

 



 

## Manage skills AI inferencing

Select __Skill inferencing by AI__ under __Settings__ to see details about the AI inferencing settings.

When inferencing is enabled, users receive AI-generated skills relevant to their role. When skills AI inferencing is turned off, no AI computation will be done for that user. The user can still create a skill profile by manually searching to add skills from your taxonomy. They can also confirm any imported skills that an admin in your organization adds for them.

Create an access control policy if you need to disable skills AI inferencing for specific users, groups, or your entire tenant, For more information, see [control access to features in Viva](/viva/feature-access-management).

> [!NOTE]
> __You can only create policies for People Skills using PowerShell at this time.  You can’t create or manage policies through the interface in Microsoft 365 admin center__

#### Details required to create access policy in Feature Access Management 

ModuleId:PeopleSkills

FeatureId: SkillsInferencing

You will have the following options while creating an access control policy to manage Skills AI inferencing:

- __Enable skills inferencing (Default):__ When inferencing is enabled, users receive an AI-generated skill profile relevant to their role. Users have the option to turn off skills AI inferencing for themselves in the __Microsoft 365__ __profile editor__, on the __Data and privacy tab__.

 

- __Keep skills inferencing enabled but default off:__  Skills inferencing is available in your tenant, but users in this access policy will be “opted-out” and will not receive AI-generated skills. Users have the option to turn it on for themselves in the __Microsoft 365__ __profile editor__, on the __Data and privacy tab__.

Admins can use the following settings in PowerShell to create this policy: 


```powershell
 Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId SkillsInferencing -Name SoftDisable -IsFeatureEnabled $true -IsUserControlEnabled $true -IsUserOptedInByDefault $false
```

 

-  __Completely Disable skills inferencing:__ Skills inferencing is disabled for your tenant and users cannot opt-in to receiving AI-generated skills. Please use the following settings in PowerShell to create this policy:


```powershell
Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId SkillsInferencing -Name HardDisable -IsFeatureEnabled $false
```

 

For more information on how to create and manage policies, see [control access to features in Viva](/viva/feature-access-management).

 

## Control Visibility of user skills profile (Parent Control)

This control can be used to control visibility of a user’s entire skills profile. An individual's skills profile consists of AI-generated skills, user-confirmed skills, and imported skills.



If you need to disable sharing for specific users, groups, or your entire tenant, create an access control policy. For more information, see [control access to features in Viva](/viva/feature-access-management).



#### Details required to create access policy in Feature Access Management 

ModuleId:PeopleSkills

FeatureId: SkillsProfileVisibility

You have the following options while creating an access control policy:

- Enable profile visibility (Default): When visibility is enabled, users skills profile is shared across M365. Users have the option to turn it off for themselves in their skill settings.

- Keep profile visibility default off:  Users in this access policy will be “opted-out”, and their skills will not be shared across M365. Users have the option to turn it on for themselves in their skill settings. Please use the following settings in PowerShell to create this policy:

   
  

```powershell
Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId SkillsProfileVisibility -Name SoftDisable -IsFeatureEnabled $true -IsUserControlEnabled $true -IsUserOptedInByDefault $false
```



For more information on how to create and manage policies, see [control access to features in Viva](/viva/feature-access-management).

## Control Visibility of AI-generated skills

AI-generated skills are provided to users based on their role and Microsoft 365 activity.

By default, a user’s AI-generated skills are shown to others in their organizations and shared with other Microsoft 365 experiences. Note: These skills are only shared if the parent control (Skills Profile visibility) is also enabled/shared. If sharing is disabled, AI suggested skills will not be shown to other users or shared with any M365 experiences.

 If you need to disable sharing for specific users, groups, or your entire tenant, create an access control policy. For more information, see [control access to features in Viva](/viva/feature-access-management).



#### Details required to create access policy in Feature Access Management 

ModuleId:PeopleSkills

FeatureId: ShowAISkills

You will have the following options while creating an access control policy:

 Enable sharing of AI-generated skills (Default): When visibility is enabled, AI-generated skills are shared in skills-driven experiences for users, leaders, and analysts in your organization. Note: These skills can only be shared if parent control (Skills Profile visibility) is also enabled/shared. Users can also manage sharing of AI-generated skills for themselves in the Microsoft 365 __profile editor__ on the __Data and privacy tab__.

 

 Default sharing off for AI-generated skills:  Users in this access policy will be “opted-out”, and their AI-suggested skills will not be shared across M365. Users have the option to turn it on for themselves in their skill settings.

Please use the following settings in PowerShell to create this policy:

 

Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId ShowAISkills -Name SoftDisable -IsFeatureEnabled $true -IsUserControlEnabled $true -IsUserOptedInByDefault $false

 

 Completely disable sharing of AI-generated skills: AI-generated skills are not shared with anyone but the user themselves and users cannot opt-in to sharing their AI-generated skills before confirming them those skills. Please use the following settings in PowerShell to create this policy:

 

Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId ShowAISkills -Name  HardDisable -IsFeatureEnabled $false

 

 <ins>Read more about </ins>[control access to features in Viva](/viva/feature-access-management).

Control Visibility of third-party imported skills

Imported skills added by an admin in your organization from external systems display in a user's skills profile alongside AI-generated skills. Like AI-generated skills, these skills are available for the user to confirm in the Microsoft 365 profile editor.

Imported skills are shared by default with others in the organization. Note: These skills can only be shared if the parent control (Skills Profile visibility) is also enabled. If sharing is disabled, imported skills won't display to others in the organization.

If you need to disable sharing for specific users, groups, or your entire tenant, create an access control policy.  Read more about [control](/viva/feature-access-management)ing  feature access.

Note: Policies for People Skills can only be created by PowerShell at this time and cannot be created or managed through the Admin Center.

__Details required to create access policy in PowerShell__

ModuleId:PeopleSkills

FeatureId: ShowOrgAddedSkills

You can  createan access control policy with the following options:

·         Enable third-party skill visibility (Default): When visibility is enabled, third-party skills are shared across M365. Note: These skills are only shared if if Skills Profile visibility is also enabledor shared. Users have the option to turn it off for themselves in their settings.

 

·         Keep third-party skill sharing default off:  Users in this access policy will be “opted-out”, and their third-party skills will not be shared across M365. Users have the option to turn it on for themselves in their skill settings.

Please use the following settings in PowerShell to create this policy:

 

Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId ShowOrgAddedSkills -Name SoftDisable -IsFeatureEnabled $true -IsUserControlEnabled $true -IsUserOptedInByDefault $false

 

·         Completely third-party skill sharing: Third-party skills are not shared with M365 experience in your tenant and users cannot opt-in to sharing their third-party skills. Please use the following settings in PowerShell to create this policy:

 

Add-VivaModuleFeaturePolicy -ModuleId PeopleSkills -FeatureId ShowOrgAddedSkills -Name  HardDisable -IsFeatureEnabled $false

 

For more information on how to create and manage policies, see [control access to features in Viva](/viva/feature-access-management).

 

