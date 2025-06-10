---
title: Monitor the status of files processed for autofill and translation in SharePoint
ms.author: chucked
author: chuckedmonson
manager: jtremper
ms.reviewer: karlha
ms.date: 06/10/2025
audience: admin
ms.topic: article
ms.service: microsoft-syntex
search.appverid: 
ms.collection: 
    - enabler-strategic
    - m365initiative-syntex
ms.localizationpriority:  medium
description: Learn how to monitor the processing status of files in a SharePoint document library.
---

# Monitor the status of files processed for autofill and translation in SharePoint

<sup>**Applies to:**  &ensp; &#10003; Autofill columns &ensp; | &ensp; &#10003; Document translation</sup>

You can now view real-time updates on files processed for autofill columns and document translation.

This feature lets you:

- See when a file is being processed.
- Check the status of the file: **In progress**, **Completed**, or **Failed**.
- Understand what worked, what didn’t, and why.

You can view and monitor the processing status for a [selected file](#monitor-the-processing-status-for-a-selected-file) or for [all files](#monitor-the-processing-status-for-all-files-in-a-library) in a document library.

<!---
The detailed view in the **View recent activity** pane If something goes wrong, you’ll get a clear error message and a link to helpful guidance—so you can fix issues quickly and keep things moving.





The processing status pane gives you full visibility into your file processing workflows with real-time updates on autofill columns and document translation. It helps you:

- Track when a file is being processed.
- See whether it’s **In progress**, **Completed**, or **Failed**.
- Understand both successful outcomes and failure reasons.

This feature helps you keep track of what’s happening with each file—every step of the way. You can see when a file starts processing, when it finishes, and if something goes wrong.

Instead of just showing one status, you now get a detailed view. You’ll know which services worked, which didn’t, and why. If there’s an issue, you’ll see a clear error message and a link to helpful documentation so you can fix it quickly.
--->

## Prerequisites

- Ensure your SharePoint library has the [autofill columns service](autofill-overview.md) or the [document translation service](translation-overview.md) enabled.

- Ensure you have permission to view or manage the library.

## Monitor the processing status for a selected file

1. In a SharePoint document library, select the file or files you want for which you want to view the status.

2. From the **More options** (**...**) menu either next to the file name or on the command bar, select **Autofill columns** > **View recent activity** or **Translate** > **View recent activity**.

    ![Screenshot of the More options menu showing Autofill columns and View recent activity.](../media/content-understanding/processing-status-view-recent-activity.png)

3. Depending on the service you selected, the **Autofill activity** panel or the **Translation activity** panel opens. [Learn more about the activity panel.](#view-the-activity-panel)

## Monitor the processing status for all files in a library

1. In a SharePoint document library, on the command bar:

    - For autofill columns, select **More options** (**...**) > **Autofill columns** > **View recent activity**.

    - For translation, select **Translate** > **View recent activity**.

<!---
1. In a SharePoint document library, on the command bar, select **Autofill columns** > **View recent activity** or **Translate** > **View recent activity**.

    ![Screenshot of the More options menu showing Autofill columns and View recent activity.](../media/content-understanding/processing-status-view-recent-activity.png)
--->

2. Depending on the service you selected, the **Autofill activity** panel or the **Translation activity** panel opens. [Learn more about the activity panel.](#view-the-activity-panel)

## View the activity panel

The activity panel shows you a list of file processing events, including:

- The file name
- A brief summary of the action that was performed, or information about why it failed
- The processing status: **In progress**, **Completed**, or **Failed**
- The date and time of the event

    ![Screenshot of the activity panel in a SharePoint library.](../media/content-understanding/processing-status-activity-panel.png)

By default, the panel shows activity for the last 60 days.

To choose a specific date range, select **Filter** > **Date range**.

To show only files that have the status of **Failed**, select **Filter** > **Failed status**.

### Status definitions

| Status       | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| In&nbsp;progress  | The service has started processing the file. A timestamp is displayed.           |
| Completed    | The service has finished processing successfully. A description of the completed actions is provided. |
| Failed       | The service has encountered an error. A description of the cause of the failure is provided. |
