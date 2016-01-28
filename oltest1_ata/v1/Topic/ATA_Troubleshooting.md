---
description: na
keywords: na
title: ATA Troubleshooting
search: na
ms.date: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 5ab62562-84d2-4af0-93ef-730839668d48
ms.author: 5f6e9ed0-302d-496f-873c-7a2b94e50410
---
# ATA Troubleshooting
There are three main sources of information for troubleshooting ATA:
logs, performance counters and the database.

## ATA Logs
The ATA logs provide insight into what each component of ATA is doing at any giving point in time.

### ATA Gateway logs
The ATA Gateway logs are located in a subfolder called Logs. In the default installation location, the  ATA Gateway logs can be found here: C:\Program Files\Microsoft Advanced Threat Analytics\Gateway\Logs. The  first three log files listed below have a maximum size of up to 50 MB, when that size is reached, a new log file is created and the previous one is archived and renamed as follows: &lt;original file name&gt;-Archived-00000,  where 00000 iterates for each archived file.

The following logs are available for the ATA Gateway:

-   Microsoft.Tri.Gateway.log – This log contains a list of  everything that happens in the ATA Gateway (including resolution of account and computer based on IP address and packet information as well as errors resolving accounts and computers).

    This log is especially useful for getting the overall status of all operations performed by the ATA Gateway in a chronological order.

-   Microsoft.Tri.Gateway-Resolution.log – This log contains details of how the ATA Gateway attempts to resolve the account and computer that performed activities based on the known IP address and packet information.

    This log is especially useful for investigating account and computer resolution  issues by the ATA Gateway.

-   Microsoft.Tri.Gateway-Errors.log – This log contains only the errors that are caught by the ATA Gateway.

    This log is especially useful for investigating issues that need to be correlated to specific times and performing health checks.

-   Microsoft.Tri.Gateway-ExceptionStatistics.log – This log groups all similar errors and exceptions and measures their count.
    This file will start empty each time the ATA Gateway service starts and is updated every minute.

    This log is especially useful for understanding if there are any new errors or issues with the ATA Gateway. Because the errors are grouped, it is easier to read to see if there are any new types of errors or issues.

### ATA Center logs
The ATA Center logs are located in a subfolder called Logs. In the default installation location, the ATA Center logs can be found here: C:\Program Files\Microsoft Advanced Threat Analytics\Center\Logs. The  first three log files listed below have a maximum size of up to 50 MB, when that size is reached, a new log file is created and the previous one is archived and renamed as follows: &lt;original file name&gt;-Archived-00000,  where 00000 iterates for each archived file.

The following logs are available for the ATA Center:

-   Microsoft.Tri.Center.log – This log contains a list of everything that happens in the ATA Center (including suspicious activity detections and errors detecting suspicious activities).

    This log is especially useful for understanding the overall status of all operations in chronological order.

-   Microsoft.Tri.Center-Detection.log – This log contains just the detection details of the center.
    Main use: investigating detection issues

