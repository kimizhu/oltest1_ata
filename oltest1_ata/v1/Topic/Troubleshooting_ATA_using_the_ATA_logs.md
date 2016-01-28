---
description: na
keywords: na
title: Troubleshooting ATA using the ATA logs
search: na
ms.date: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: b8ad5511-8893-4d1d-81ee-b9a86e378347
ms.author: 5f6e9ed0-302d-496f-873c-7a2b94e50410
---
# Troubleshooting ATA using the ATA logs
<?xml version="1.0" encoding="UTF-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
    <introduction>
        <para>The ATA logs provide insight into what each component of ATA is doing at any giving point in time.</para>
    </introduction>
    <section>
        <title>ATA Gateway logs</title>
        <content>
            <para>The ATA Gateway logs are located in a subfolder called <ui>Logs </ui>. In the default installation location, it can be found at: <ui>C:\Program Files\Microsoft Advanced Threat Analytics\Gateway\Logs</ui>.</para><para>The ATA Gateway has the following logs: 
</para>
        <list class="bullet"><listItem><para>	Microsoft.Tri.Gateway.log – This log contains everything that happens in the ATA Gateway (including resolution and errors).
</para><para>Main use: Getting the overall status of all operations in the chronological order in which they occurred.
</para></listItem><listItem><para>	Microsoft.Tri.Gateway-Resolution.log – This log contains the resolution details of the entities seen in traffic by the ATA Gateway.
</para><para>Main use: Investigating resolution issues of entities.</para></listItem><listItem><para>Microsoft.Tri.Gateway-Errors.log – This log contains just the errors that are caught by the ATA Gateway.
</para><para>Main use: Performing health checks and investigating issues that need to be correlated to specific times.</para></listItem><listItem><para>	Microsoft.Tri.Gateway-ExceptionStatistics.log – This log groups all similar errors and exceptions, and measures their count.
This file starts out  empty each time the ATA Gateway service starts and is updated every minute.
</para><para>Main use: Understanding if there are any new errors or issues with the ATA Gateway  - because the errors are grouped it is easier to read and see if there is a new type of error or issue.</para></listItem></list><alert class="note">
 <para>The first three log files have a maximum size of up to 50 MB. When that size is reached, a new log file is opened and the previous one is renamed to "&lt;original file name&gt;-Archived-00000" where the number increments each time it is renamed.

</para>
</alert></content>
        <sections>
            <section>
                <title>ATA Center logs</title>
                <content>
                    <para>The ATA Center logs are located in a subfolder called <ui>Logs </ui>. In the default installation location, it can be found at: <ui>C:\Program Files\Microsoft Advanced Threat Analytics\Center\Logs</ui>".</para><para>The ATA Center has the following logs: 
</para>
                <list class="bullet"><listItem><para>	Microsoft.Tri.Center.log – This log contains everything that happens in the ATA Center, including detections and errors.
</para><para>Main use: Getting the overall status of all operations in the chronological order in which they occurred.
</para></listItem><listItem><para>	Microsoft.Tri.Center-Detection.log – This log contains just the detection details of the ATA Center.
</para><para>Main use: Investigating detection issues 
.</para></listItem><listItem><para> 
Microsoft.Tri.Center-Errors.log – This log contains just the errors that are caught by the ATA Center.
</para><para>Main use: Performing health checks and investigating issues that need to be correlated to specific times.</para></listItem><listItem><para>	Microsoft.Tri.Center-ExceptionStatistics.log – This log groups all similar errors and exceptions, and measures their count.
This file starts out empty each time the ATA Center service starts and is updated every minute.
</para><para>Main use: Understanding if there are any new errors or issues with the ATA Center - because the errors are grouped it is easier to read and see if there is a new type of error or issue.
</para></listItem></list><alert class="note">
 <para>The first thee log files have a maximum size of up to 50 MB. When that size is reached, a new log file is opened and the previous one is renamed to "&lt;original file name&gt;-Archived-00000" where the number increments each time it is renamed.

</para>
</alert></content>
            </section>
        <section>
<title>ATA Console logs</title><content><para>The ATA console logs (the management API logs) are located in a subfolder called <ui>Logs </ui>. In the default installation location, it can be found at: <ui>C:\Program Files\Microsoft Advanced Threat Analytics\Center\Management\Logs</ui>.
</para><para>The ATA Console has the following logs:
</para><list class="bullet"><listItem><para>w3wp.log – This log contains everything that happens in the management process (IIS). 
</para><para>Main use: </para></listItem><listItem><para>w3wp-Errors.log – This log contains just the errors that are caught by the management process (IIS). 

</para><para>Main use:</para></listItem><listItem><para>8e75f9f1-ExceptionStatistics.log – This log groups all similar errors and exceptions and measures their count.
This file will start empty each time the gateway service will start and is updated every minute.
</para><para>Main use: Understanding if there are any new errors or issues with the ATA Center  - because the errors are grouped it is easier to read and see if there is a new type of error or issue.</para></listItem></list><alert class="note">
 <para>The first two log files have a maximum size of up to 50 MB. When that size is reached, a new log file is opened and the previous one is renamed to "&lt;original file name&gt;-Archived-00000" where the number increments each time it is renamed.

</para>
</alert></content>
</section><section>
<title>ATA Deployment logs</title><content><para>	The ATA deployment logs (installation) are located in the temp directory for the user who installed the product. In the default installation location, it can be found at: default: C:\Users\Administrator\AppData\Local\Temp (or one directory above %temp%).</para><para>ATA Center deployment logs:</para><list class="bullet"><listItem><para>Microsoft Advanced Threat Analytics Center_20150601104213.log</para></listItem><listItem><para>Microsoft Advanced Threat Analytics Center_20150601104213_0_MongoDBPackage.log</para></listItem><listItem><para>	Microsoft Advanced Threat Analytics Center_20150601104213_1_MsiPackage.log</para></listItem></list><para>ATA Gateway deployment logs:</para><list class="bullet"><listItem><para>	Microsoft Advanced Threat Analytics Gateway_20151214014801.log</para></listItem><listItem><para>	Microsoft Advanced Threat Analytics Gateway_20151214014801_001_MsiPackage.log</para></listItem></list></content>
</section></sections>
    </section>
    <relatedTopics/>
</developerConceptualDocument>
