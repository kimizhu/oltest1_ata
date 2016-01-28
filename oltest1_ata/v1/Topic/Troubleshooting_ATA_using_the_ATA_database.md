---
description: na
keywords: na
title: Troubleshooting ATA using the ATA database
search: na
ms.date: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d89e7aff-a6ef-48a3-ae87-6ac2e39f3bdb
ms.author: 5f6e9ed0-302d-496f-873c-7a2b94e50410
---
# Troubleshooting ATA using the ATA database
<?xml version="1.0" encoding="UTF-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
    <introduction>
        <para>ATA uses MongoDB as its database.
You can interact with the database using the default command line or using a user interface tool that you download  to perform advanced tasks and troubleshooting.</para>
    </introduction>
    <section>
        <title>Interacting with the database</title>
        <content>
            <para>The default and most basic way to query the database is using the Mongo shell:</para>
        <list class="ordered"><listItem><para>	Open a command line window and change the path to the MongoDB bin folder. The default path is : <ui>C:\Program Files\Microsoft Advanced Threat Analytics\Center\MongoDB\bin</ui>.
</para></listItem><listItem><para>Run: <codeInline>mongo.exe ATA</codeInline>. Make sure to type ATA with all capital letters.</para></listItem></list><table border="1"><thead><tr><TD><para>How to...</para></TD><TD><para>Syntax</para></TD><TD><para>Notes</para></TD></tr></thead><tbody><tr><TD><para>Check for collections in the database.</para></TD><TD><para><codeInline>show collections</codeInline></para></TD><TD><para>Useful as an end-to-end test to see that traffic is being written to the database and that event 4776 is being received by ATA.</para></TD></tr><tr><TD><para>Get the details of a user/computer/group (UniqueEntities), such as user  ID.</para></TD><TD><para><codeInline>db.UniqueEntities.find({SearchNames: "&lt;name of entity in lower case&gt;"})</codeInline></para></TD><TD></TD></tr><tr><TD><para>Find Kerberos authentication traffic originating from a specific computer on a specific day.</para></TD><TD><para><codeInline>db.KerberosKdcs_&lt;date&gt;.find({SourceComputerId: "&lt;Id of the source computer&gt;"})</codeInline></para></TD><TD><para>To get the &lt;ID of the source computer&gt; you can query the UniqueEntity collections, as shown in the example.</para><para>Each network activity type, for example Kerberos authentications, has its own collection per UTC date.
</para></TD></tr><tr><TD><para>Find NTLM traffic originating from a specific computer related to a specific account on a specific day.</para></TD><TD><para><codeInline>db.Ntlms_&lt;date&gt;.find({SourceComputerId: "&lt;Id of the source computer&gt;", SourceAccountId: "&lt;Id of the account&gt;"})</codeInline></para></TD><TD><para>To get the &lt;ID of the source computer&gt; and &lt;ID of the account&gt; you can query the UniqueEntity collections, as shown in the example.</para><para>Each network activity type, for example NTLM authentications, has its own collection per UTC date.</para></TD></tr><tr><TD><para>Search for advanced properties such as the active dates of an account. For example you may want to know if an account has at least 21 days of activity for the abnormal behavior machine learning algorithm to be able to run on it.</para></TD><TD><para><codeInline>db.Profiles.find({UniqueEntityId: "&lt;Id of the account&gt;")</codeInline></para></TD><TD><para>To get the &lt;ID of the account&gt; you can query the UniqueEntity collections, as shown in the example.</para><para>The property name that shows the dates in which the account has been active is called: "ActiveDates"
.</para></TD></tr><tr><TD><para>Make advanced configuration changes. In this example we change the send queue size for all ATA Gateways to 10,000.</para></TD><TD><para><codeInline>db.SystemProfiles.update( {_t: "GatewaySystemProfile"} , </codeInline></para><para><codeInline>{$set:{"Configuration.EntitySenderConfiguration.EntityBatchBlockMaxSize" : "10000"}})</codeInline></para></TD><TD><para>For example, if you are investigating a suspicious activity that occurred on the 20/10/2015 and want to learn more about the NTLM activities that "John Doe" performed on that day. 
</para><para>First, find the ID of "John Doe"
db.UniqueEntities.find({Name: "John Doe"})</para><para>
Take a note of his ID as indicated by the value of "_id" in our example let's assume the ID is "123bdd24-b269-h6e1-9c72-7737as875351"</para><para>Then, search for John Doe's account NTLM activities:</para><para>
<codeInline>db.Ntlms_20151020.find({SourceAccountId: "123bdd24-b269-h6e1-9c72-7737as875351"})
</codeInline></para></TD></tr></tbody></table></content>
        
    </section>
    <section>
<title>ATA Configuration</title><content><para>The configuration of ATA is stored in the "SystemProfiles" collection in the database.

This collection is backed up every hour by the ATA Center service to a file called: "SystemProfiles.json". This is located in a subfolder called "Backup". In the default ATA installed location it can be found here:  <ui>C:\Program Files\Microsoft Advanced Threat Analytics\Center\Backup\SystemProfiles.json</ui>. It is recommended that you back up this file somewhere when making major changes to ATA.
It is possible to restore all the settings by running the following command:
</para><para><codeInline>mongoimport.exe --db ATA --collection SystemProfiles --file "&lt;SystemProfiles.json backup file&gt;" --upsert
</codeInline></para></content>
</section><relatedTopics/>
</developerConceptualDocument>
