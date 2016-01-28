---
description: na
keywords: na
title: Troubleshooting ATA Monitoring Alerts
search: na
ms.date: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 51bedf1f-b267-4e68-b12c-2d43db17e82d
ms.author: 5f6e9ed0-302d-496f-873c-7a2b94e50410
---
# Troubleshooting ATA Monitoring Alerts
<?xml version="1.0" encoding="UTF-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
    <introduction>
        <para>This article lists the ATA monitoring alerts with a resolution process for each.</para>
    </introduction>
    <section>
        <title>Dropped Port Mirrored Network Traffic</title>
        <content>
            <para>
This alert indicates that the ATA Gateway is dropping the traffic that it is receiving on its capture network adapter(s)
This could be the results of either resource issues (such as CPU or memory) or an ATA component that is not keeping up.

Refer to the ATA Performance counters guide to understand how to locate the bottleneck that is causing the ATA Gateway to drop traffic.</para>
        </content>
        
    </section>
    <section>
<title>Failed to Connect to Domain Controller</title><content><para><?xm-replace_text Type new maml:para here ?></para></content>
</section><section>
<title>ATA Gateway Stopped Communicating</title><content><para><?xm-replace_text Type new maml:para here ?></para></content>
</section><section>
<title>ATA Center at Maximum Capacity</title><content><para><?xm-replace_text Type new maml:para here ?></para></content>
</section><section>
<title>Known Errors</title><content><table border="1"><thead><tr><TD><para>Error</para></TD><TD><para>Description</para></TD><TD><para>Resolution</para></TD></tr></thead><tbody><tr><TD><para>System.DirectoryServices.Protocols.LdapException: A local error occurred</para></TD><TD></TD><TD><para>DNS resolution</para><para>

Time sync with domain

</para><para>CRL
</para></TD></tr><tr><TD><para>System.ServiceModel.FaultException: At least one security token in the message could not be validated.</para></TD><TD></TD><TD><para>Certificate issues</para></TD></tr><tr><TD><para>System.IdentityModel.Tokens.SecurityTokenValidationException: Failed to validate certificate chain</para></TD><TD></TD><TD><para>Trusted CA CRL</para></TD></tr><tr><TD><para>System.Net.Sockets.SocketException: No connection could be made because the target machine actively refused it 127.0.0.2:443</para></TD><TD></TD><TD><para>MongoDB</para></TD></tr><tr><TD><para>System.ServiceModel.EndpointNotFoundException: Could not connect to net.tcp://center.ip.addr:443/IEntityReceiver</para></TD><TD></TD><TD><para>Connectivity to SIEM</para></TD></tr><tr><TD><para>Microsoft.Common.ExtendedException: Failed to parse time generated</para></TD><TD></TD><TD><para>SIEM configuration</para></TD></tr><tr><TD><para>System.DirectoryServices.Protocols.LdapException: The LDAP server is unavailable.</para></TD><TD></TD><TD><para>AD Permissions on objects</para></TD></tr><tr><TD><para>System.ServiceModel.FaultException: An error occurred when verifying security for the message.</para></TD><TD></TD><TD><para>Time sync between ATA Gateway and ATA Center</para></TD></tr><tr><TD><para>Microsoft.Tri.Infrastructure.ContractException: Contract exception</para></TD><TD></TD><TD><para>Finish the configuration</para></TD></tr></tbody></table></content>
</section><relatedTopics/>
</developerConceptualDocument>
