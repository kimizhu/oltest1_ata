---
description: na
keywords: na
title: ATA technical FAQ
search: na
ms.date: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a7d378ec-68ed-4a7b-a0db-f5e439c3e852
ms.author: 5f6e9ed0-302d-496f-873c-7a2b94e50410
---
# ATA technical FAQ
<?xml version="1.0" encoding="UTF-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd" xmlns:xlink="http://www.w3.org/1999/xlink">
    <introduction>
        <para>This article provides a list of frequently asked questions about ATA and provides insight and answers.</para>
    </introduction>
    <section>
        <title>ATA Frequently Asked Questions</title>
        <content>
            
        <table border="1"><thead><tr><TD><para>Question</para></TD><TD><para>What you should do to fix it...</para></TD></tr></thead><tbody><tr><TD><para>The ATA Gateway won't start, what should I do?</para></TD><TD><para>Look at the most recent error in the current error log (Where ATA is installed under the "Logs" folder)</para></TD></tr><tr><TD><para>How can I test ATA?</para></TD><TD><para>You can simulate suspicious activities which is an end to end test by doing one of the following:</para><list class="ordered"><listItem><para>DNS reconnaissance by using Nslookup.exe
</para></listItem><listItem><para>Remote execution by using psexec.exe

</para></listItem></list><para>This needs to run against the domain controller being monitored and not from the gateway

</para></TD></tr><tr><TD><para>How do I verify Windows Event Forwarding?</para></TD><TD><para>You can run the following from a command prompt at the  \Program Files\Microsoft Advanced Threat Analytics\Center\MongoDB\bin directory:

</para><para><codeInline>mongo ATA --eval "printjson(db.getCollectionNames())" | find /C "NtlmEvents"
</codeInline></para></TD></tr><tr><TD><para>Does ATA work with encrypted traffic?</para></TD><TD><para>Encrypted traffic will not be analyzed (for example: LDAPS, IPSEC ESP).</para></TD></tr><tr><TD><para>How many ATA Gateways do I need?</para></TD><TD><para>There are two things to consider when figuring out how many gateways you would need:</para><list class="bullet"><listItem><para>The total amount of traffic your domain controllers are producing would tell you what is the minimum amount of gateways that would be able to handle your AD environment from a performance perspective.
To read more on how to gather the amount of traffic your domain controllers are producing and the <link xlink:href="279d79f2-962c-4c6f-9702-29744a5d50e2">ATA Capacity Planning</link>.</para></listItem><listItem><para>The operational limitation of the port mirroring would tell you how many gateways you would need for all domain controllers, for example: per switch, per datacenter, per region – every environment would have its own consideration.</para></listItem></list></TD></tr><tr><TD><para>How much storage do I need for ATA?</para></TD><TD><para>For every one full day with an average of 1000 packets/sec you would need 1.5GB of storage.</para><para>For more information see, <link xlink:href="279d79f2-962c-4c6f-9702-29744a5d50e2">ATA Capacity Planning</link>.</para></TD></tr><tr><TD><para>Why are certain accounts sensitive?</para></TD><TD><para>This happens when an account is a member of certain groups which we designate as sensitive (for example: "Domain Admins").
To understand why an account is sensitive you can go over its group membership to understand what are the sensitive groups it belongs to (the group that it belongs to can also be sensitive due to another group so the same process should be performed till reaching the root group that is sensitive).</para></TD></tr><tr><TD><para>How do I monitor a virtual domain controller?</para></TD><TD><para>You can have either a virtual or physical gateways as described in <link xlink:href="cdaddca3-e26e-4137-b553-8ed3f389c460">Configure Port Mirroring</link>.  
The easiest way would probably be to have a virtual gateway in every host where a virtual domain controller exists.

In case your virtual domain controllers are moving between hosts you would need to do either:
</para><list class="bullet"><listItem><para>When the virtual domain controller moves to another host the gateway in that host would be preconfigured to get the traffic from that recently moved virtual domain controller.</para></listItem><listItem><para>Make sure that you affinitive the virtual gateway to the virtual domain controller so that if it is moved the gateway moves with it</para></listItem><listItem><para>There are some virtual switches that can send traffic between hosts.</para></listItem></list></TD></tr><tr><TD><para>How do I back up ATA?</para></TD><TD><para>There are 2 things that would potentially need to be backed up:
</para><list class="bullet"><listItem><para>The configuration of ATA is stored in the database and is being backed up every hour, please read: &lt;need URL once the article is online&gt;</para></listItem><listItem><para>The traffic and events stored by ATA can be backed up by any supported procedure of backing up the entire database, for more information see <link xlink:href="1d27dba8-fb30-4cce-a68a-f0b1df02b977">ATA Database Management</link></para></listItem></list></TD></tr><tr><TD><para>What can ATA detect?</para></TD><TD><para>For the full list of ATA detections, see <link xlink:href="a315cf03-c5a3-4ecb-a0f8-4d3e322e6ad1">Microsoft Advanced Threat Analytics</link>.</para></TD></tr></tbody></table></content>
        
    </section>
    <relatedTopics/>
</developerConceptualDocument>
