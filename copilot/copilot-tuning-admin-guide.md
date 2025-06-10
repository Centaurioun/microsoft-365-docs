---
title: "Microsoft 365 Copilot Tuning Admin Guide (Preview)"
f1.keywords:
ms.author: lauragra
author: lauragra
manager: calvind
ms.date: 06/17/2025
audience: Admin
ms.topic: overview
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection: 
- m365copilot
- magic-ai-copilot
description: "Find admin guidance for enabling Copilot Tuning in your organization."
---

# Microsoft 365 Copilot Tuning admin guide (preview)

Microsoft 365 Copilot Tuning enables organizations to securely fine-tune large language models (LLMs) using tenant-specific data, and to deploy those fine-tuned models as declarative agents within Microsoft 365 Copilot. As an AI Admin, you retain full control over who can fine-tune models, how they are published, and how they are governed throughout their lifecycle.

This article provides information about the governance controls that are available for Copilot Tuning in the Microsoft 365 admin center.

> [!NOTE]
> Copilot Tuning is currently available for Early Access Preview (EAP).

## Prerequisites

To manage Copilot Tuning governance controls, make sure that you meet the following prerequisites:

- Copilot Tuning Early Access Preview (EAP) enrollment. To enroll in the EAP:
    - Your tenant must have at least 5,000 active Microsoft 365 Copilot licenses.
    - An AI Admin must accept the EAP terms on behalf of the organization.
    > [!NOTE]
    > If your tenant doesn't show Copilot Tuning, contact Microsoft support or your account team to request EAP provisioning.
- You must have one of the following roles:
    - Global Administrator
    - AI Administrator (if defined as a custom role in your organization)
- Copilot extensibility is enabled via Copilot Settings in your organization. For more information, see [Manage agents for Microsoft 365 Copilot in the Microsoft 365 admin center](/microsoft-365/admin/manage/manage-copilot-agents-integrated-apps?view=o365-worldwide#enable-or-disable-copilot-extensibility).
- Power Platform

## What is Copilot Tuning?

Copilot Tuning is a self-serve, secure Microsoft 365 offering for fine-tuning LLMs using your organization's own data. It allows for a self-service workflow where model makers select datasets and Copilot Studio seamlessly handles data preparation, model training, and evaluation. This is suited for low-code domain adaptation tasks with minimal engineering overhead. After a model is fine-tuned, it can be published as a declarative agent in Microsoft 365 Copilot. These agents surface in Word, Teams, Outlook, and other Microsoft 365 apps to perform tasks such as legal clause generation, incident report summarization, or contract drafting.

For more information, see [Copilot Tuning overview](copilot-tuning-overview.md).

## Enable Copilot Tuning

To activate the Copilot Tuning service and scope its availability:

1. Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in with your Global Administrator or AI Administrator account.
2. Go to **Copilot** > **Copilot settings**. The settings for Copilot Tuning are in this section.
    [image placeholder]
3. Choose **Copilot Tuning**, and choose **Accept** to accept the EAP terms.
    
    > [!NOTE]
    > The **Copilot Tuning** setting is only available if your tenant meets the criteria described in the [Prerequisites](#prerequisites) section.

    [image placeholder]

4. Choose **Specific users in your organization** and add the who in your organization who can create task-specific models. For more information, see [Scope access and permissions](#scope-access-and-permissions).

## Scope access and permissions

Fine-grained access controls ensure that only authorized users within the tenant can initiate fine-tuning or publishing models. You can manage this access by specifying users and security groups for these controls.

### Configure model makers

Designate users who are authorized to use Copilot Tuning to fine tune task-specific models. These model makers are generally SMEs within a particular part of the organization like marketing, finance, or legal. The users that you designate at model makers are then able to access the Copilot Tuning workflow in Copilot Studio.

You can designate up to 10 users to be model makers. If you need more than 10 model makers in your organization, reach out to Copilot Tuning support or your Microsoft account team.

When you add a user to Copilot Tuning, they receive an email with instructions to get started. You can also use the **Copilot Tuning** control in the admin center to remove users from Copilot Tuning.

### Manage tuned task-specific models

You can review and manage the set of models that model makers create and publish via the **Copilot Tuning** control in the admin center.

[image placeholder]

Choose any published model to review the associated security groups and update them as needed.

[image placeholder]

You can also remove a published model by choosing **Remove this model**.

## Related content