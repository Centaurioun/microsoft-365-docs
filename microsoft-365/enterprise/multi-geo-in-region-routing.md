---
title: "Configure Multi-Geo In-Region Routing"
ms.reviewer:
ms.date: 07/02/2025
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: how-to
ms.service: microsoft-365-enterprise
ms.subservice: multi-tenant
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
ms.collection: 
- Strat_SP_gtc
- must-keep
description: Learn how to configure the Multi-Geo In-Region Routing.
---

# Configure Multi-Geo In-Region Routing

This article describes the process of configuring multi-geo in-region routing.

## Overview

Multi-Geo In-Region Routing (IRR) enables customers to control the routing of inbound emails to comply with regional data regulations. IRR ensures that emails sent to users within specific geo-regions are processed and stored in their respective region. By directing emails to accepted domains that are associated with specific geo-regions and users located in those same geo-regions, IRR ensures that emails are fully processed and stored in the user's region. This processing and storage of emails keeps the data within the user’s Preferred Data Location (PDL), enhancing data sovereignty and compliance.

To enable IRR for Exchange Online, you need to use PowerShell cmdlets to configure the settings for each domain you plan to enable with the feature.

## Prerequisites

1. The domain you want to enable with IRR must be added to the Exchange Admin Center (EAC) as an accepted domain.
1. For IRR to apply to specific users, you need to make the IRR-enabled domain be the user’s primary domain. Additionally, the user’s PDL must align with the domain’s mail flow region. This alignment ensures that the mail is processed in the same region as the region in which the email is stored. You must use one of the 3-letter codes specified in [Microsoft 365 Multi-Geo availability](microsoft-365-multi-geo.md#microsoft-365-multi-geo-availability)as the **PreferredDataLocation** value for the user, as these are the regions that support IRR.
1. IRR requires the user to have a Microsoft 365 Multi-Geo license and a second license of any SKU type that grants email capabilities.
1. IRR requires the usage of an MX target in mx.microsoft, a domain that is DNSSEC enabled. If your contosotest.com domain isn't DNSSEC enabled, mail flow continues to work as expected but DNSSEC-validations don't occur. If your contosotest.com domain is DNSSEC enabled, mail flow continues to work and you benefit from the extra security of DNSSEC.

### Adopting an MX target

To adopt an MX target in mx.microsoft, follow these steps:

1. Update the TTL (Time To Live) of your existing MX record to the lowest TTL possible (but not lower than 30 seconds). Then, wait for the previous TTL to expire before proceeding. For example, if the TTL of your existing MX record was '3,600 seconds' or '1 hour' before you changed it, you need to wait 1 hour before proceeding to the next step.
1. Connect to Exchange Online PowerShell.
1. For the domain that you want to enable with IRR, run the following command:

   ```PowerShell
   Enable-DnssecForVerifiedDomain -DomainName <DomainName>
   ```

   In the preceding example-command, replace "domain" with the name of your chosen domain, for example, contosotest.com. For example, the command you execute will look like as shown in the following command:

   ```PowerShell
   Enable-DnssecForVerifiedDomain -DomainName contosotest.com
   ```

   > [!NOTE]
   > This command can take a few minutes to execute.

   The successful execution of the command that you had run is indicated by the following output:

   |Result  |DnssecMxValue  |ErrorData  |
   |---------|---------|---------|
   |Success     |contosotest-com.o-v1.mx.microsoft         |         |

   The output (indicating the successful execution of the command) provides the MX value for the domain. This value—**contosotest-com.o-v1.mx.microsoft**—is the name that the new MX record points to for the domain you're enabling with IRR.

1. Take the "DnssecMxValue" value, navigate to the DNS registrar hosting the domain, add a new MX record using the value **contosotest-com.o-v1.mx.microsoft**, set the TTL to the lowest possible value (but not lower than 30 seconds), and set the priority of the new MX record to **20**.

   If you're using a third-party email gateway (for example, Proofpoint), leave the MX record value so that it stays pointing to the third party. Instead, change the smarthost name that the third party uses to relay your mail to Exchange Online after the third party completes the processing on their side. The smarthost name for the domain enabled with IRR needs to be changed so that this changed smarthost name is set to be the "DnssecMxValue." This changing of the smarthost name ensures that inbound email to Exchange Online for domains using third-party email gateways are processed by Exchange Online using IRR.

1. Verify that the new MX is working via the Inbound SMTP Email test by performing the following step: 
    1. Execute the test steps in https://testconnectivity.microsoft.com/tests/O365InboundSmtp/input.

       > [!NOTE]
       > You may have to retry this test, depending on DNS caching.

    Once you complete the verification process, you view the resultant screen as depicted in the following screenshot:

    :::image type="content" source="../media/connectivity-test-results.png" alt-text="Screenshot that shows the results of the Connectivity Test process." lightbox="../media/connectivity-test-results.png":::

    This resultant screen denotes that the Mail Exchanger ending in mx.microsoft was successfully tested and that the new MX is working as expected.

1. Change the priority of the legacy MX pointing to mail.protection.outlook.com to **30**; change the priority of the MX record with the value **contosotest-com.o-v1.mx.microsoft** to priority **0** (highest priority).
1. Delete the legacy MX record ending with "mail.protection.outlook.com," "mail.eo.outlook.com," or "mail.protection.outlook.de." Then, update the TTL for the MX record ending with "mx.microsoft" to **3600 seconds**.

## Configuring IRR

Once you comply with the [Prerequisites](#prerequisites), configure the IRR by performing the following steps:

1. Connect to an Admin account for your test tenant using Exchange Online PowerShell by running the following command:
  
   ```PowerShell
   Connect-ExchangeOnline -UserPrincipalName <username>
   ```

   > [!NOTE]
   > Open PowerShell using the "Run as Administrator" mode.

2. Run the following command  to set the **MailFlowRegion** attribute's value for the domain to whatever secondary region you want it to be aligned:

   ```PowerShell
   Set-AcceptedDomain <domain> -MailFlowRegion <PreferredDataLocation Value>
   ```

   > [!NOTE]
   > You must use one of the 3-letter codes specified in [Microsoft 365 Multi-Geo availability](microsoft-365-multi-geo.md#microsoft-365-multi-geo-availability)as the **PreferredDataLocation** value for the user, as these are the regions that support IRR.

   The IRR is configured and enabled.

3. Wait for 30 minutes after enabling IRR to allow previously cached DNS records to expire and updated routing information to propagate. Once this time (of 30 minutes) has passed, send an email to that domain to verify whether the mail flow is working as expected.

Once you send the email to that domain, if you view error messages, such messages denote that the mail flow isn't working as expected. For more information on the error messages, see [Potential errors](#potential-errors).

### Potential errors

This section describes the types of error messages that are displayed if the mail flow isn't working as expected as a result of an IRR configuration failure.

The types of errors are:

- [Wrong region error](#wrong-region-error)
- [System errors](#system-errors) 

#### Wrong region error

|Error message |Description  |
|---------|---------|
|451 4.4.62 Mail sent to the wrong Office 365 region. ATTR35. For more information please go to https://go.microsoft.com/fwlink/?linkid=865268     |This SsMTP error is returned when an email server tries to deliver a message to a tenant’s wrong M365 endpoint. However, tenants for whom multi-geo SKU and IRR are enabled shouldn't get this error if the message is being delivered to one of the tenant’s [AllowedMailboxRegions](administering-exchange-online-multi-geo.md).         |

#### System errors

The following SMTP errors indicate a temporary system error. An email server is expected to retry message delivery in such cases:

- 451 4.4.3 Temporary server error. Please try again later ATTR3.4
- 451 4.3.2 Temporary server error. Please try again later ATTR55
- 451 4.4.3 Temporary server error. Please try again later ATTR55.1
