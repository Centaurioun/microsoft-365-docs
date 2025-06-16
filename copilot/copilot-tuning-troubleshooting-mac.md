---
title: "Troubleshoot the Microsoft 365 Admin Center task fine-tuning"
f1.keywords:
ms.author: emrek
author: emrekiciman
manager: calvind
ms.date: 06/17/2025
audience: Admin
ms.topic: troubleshooting
ms.service: microsoft-365-copilot
ms.localizationpriority: medium
ms.collection:
- m365copilot
- magic-ai-copilot
description: Find information about how to troubleshoot the Microsoft 365 admin center when using Copilot Tuning to fine-tune models.
---

# Troubleshoot the Microsoft 365 admin center task fine-tuning

This article describes some of the most common issues with the Microsoft 365 admin center when using Microsoft 365 Copilot Tuning to fine-tune models how to troubleshoot them.

[!INCLUDE [copilot-tuning-preview](includes/copilot-tuning-preview.md)]

## I don't see the task-specific models in the settings

Task-specific models should always be available. If you don't see them, make sure you have the required licenses and permissions. You need at least 5,000 Copilot licenses for this feature to be available.

## Admin doesn't see the task-specific models

If an admin doesn't see the task-specific models, they might have eligibility issues. Make sure you have the necessary licenses and permissions. If if the admin istn't eligible, an error is displayed with possible causes.

## Setup is taking more than 5 minutes

If the setup takes more than 5 minutes, it might be due to service failures or other issues. If the setup is not completed within an hour, reach out to support.

## Managing access to the task-specific models

Admins can manage access to the task-specific models by adding specific users to the organization. When added, users receive an email with a link to the model.

## I accidentally deleted a model

If a model is deleted, it can't be recovered. Make sure you have the correct permissions and take necessary precautions to avoid accidental deletions.

## Insufficient training data

If the training data is insufficient, you get an error message. Make sure you have enough training data after filtering.

## While completing the configuration, I get an error message

If you see an error message during the configuration, retry the process after some time. It might be due to service outages or other temporary issues.

## Errors related to knowledge sources

If you enter a link to a knowledge source you don't have access to, an error message is displayed. Make sure you have access to the required knowledge sources.

## Validation fails during the training process

If the validation fails, make sure all required fields are filled. If you ask seven questions, all seven must be answered.

## Security group coverage issues

If the selected security groups don't have access to the required knowledge sources, choose a suggested set of security groups to share with. Make sure permissions are correctly set, and wait for them to sync.

### Related content

- [Microsoft 365 Copilot Tuning overview (preview)](copilot-tuning-overview.md)

If you need support or want to provide feedback, see [Copilot Tuning FAQ](/copilot/copilot-tuning-faq.yml).



