---
title: "Trial user guide: Microsoft 365 Business Premium"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: deniseb
audience: Admin
ms.topic: article
ms.collection:
- m365-security
- tier2
- trust-pod
ms.service: microsoft-365-business-security
ms.date: 05/31/2024
ms.reviewer: nehabha
ms.localizationpriority: medium
search.appverid:
- MOE150
- MET150
description: "Make the most of your Microsoft 365 Business Premium trial. Try out some of the key productivity and security capabilities."
---

# Trial user guide: Microsoft 365 Business Premium

Welcome to the Microsoft Business Premium trial user guide! This guide helps you make the most of your free trial. You can see firsthand how Microsoft 365 Business Premium increases productivity and helps safeguard your organization with advanced security capabilities. Use this guide to set up your threat protection features, analyze detected threats, and respond to cyberattacks.

## Set up the Microsoft 365 Business Premium trial

When you [start a trial or purchase Microsoft 365 Business Premium](get-microsoft-365-business-premium.md), your first step is to get everything set up.

> [!TIP]
> Save this trial user guide to your browser favorites. When links in the trial user guide take you away from this location, it'll be easier to return to this guide to continue.

1. [Set up your trial](m365-business-premium-setup.md)!

   After you start your trial and complete the setup process, it can take up to two hours for changes to take effect.

2. [Turn on multifactor authentication](m365bp-turn-on-mfa.md) (MFA). You can use security defaults to get set up right away, or use Conditional Access policies to meet more stringent requirements.

3. Use your [preset security policies](/defender-office-365/preset-security-policies). These policies represent a baseline protection profile that's suitable for most users. Standard protection includes:

   - [Safe Links](/defender-office-365/safe-links-about), [Safe Attachments](/defender-office-365/safe-attachments-about) and [Anti-Phishing](/defender-office-365/anti-phishing-protection-about) policies that are scoped to the entire tenant or the subset of users you choose during the trial setup process. (Your trial subscription is for up to 25 users.)

   - Protection for productivity apps, such as [SharePoint](/sharepoint/introduction), [OneDrive](/onedrive/one-drive-quickstart-small-business), [Microsoft 365 Apps](/deployoffice/about-microsoft-365-apps), and [Microsoft Teams](/microsoftteams/teams-overview).

## Add a domain

When you try or buy Microsoft 365 Business Premium, you can use your own domain, or purchase one during the sign-up process.

> [!NOTE]
> If you purchased a new domain when you signed up, your domain is all set up and you can move to Add users and assign licenses. Go to the admin center(<https://admin.microsoft.com>).

1. From the admin center menu, choose **Setup** to start the wizard.

2. Select **Set up email with a custom domain** and then, **Use a domain you already own** such as `contoso.com`.

3. Follow the rest of the steps in the wizard to complete the process.

   > [!Important]
   > If you purchased a domain during the sign-up, you will not see the **Add a domain** step here. Go to **Add users** instead.

4. Follow the steps in the wizard to [create DNS records at any DNS hosting provider for Office 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) that verifies you own the domain. If you know your domain host, see [Add a domain to Microsoft 365](/microsoft-365/admin/setup/add-domain).

5. If your hosting provider is GoDaddy or another host enabled with domain connect, you're asked to sign in and let Microsoft authenticate on your behalf automatically.

## Onboard and protect devices

Microsoft 365 Business Premium includes Defender for Business, a new security solution to protect devices. See [Onboard devices to Microsoft Defender for Business](/defender-business/mdb-onboard-devices).

1. Go to the Microsoft Defender portal (<https://security.microsoft.com>) and sign in.

2. Go to **Assets** > **Devices**. If Defender for Business isn't already set up, you're prompted to run the [setup wizard](/defender-business/mdb-setup-configuration).

3. [Onboard devices](/defender-business/mdb-onboard-devices).

4. [Review your security policies](/defender-business/mdb-configure-security-settings).

## Use Microsoft 365 Apps on devices

1. Start by [installing Microsoft 365 Apps](m365bp-users-install-m365-apps.md).

2. Go to <https://m365.cloud.microsoft/> and sign in. (See [Getting Started at Office.com](https://support.microsoft.com/office/get-started-at-office-com-91a4ec74-67fe-4a84-a268-f6bdf3da1804).)

3. Create an Office document, such as a [Word document](https://support.microsoft.com/office/basic-tasks-in-word-87b3243c-b0bf-4a29-82aa-09a681999fdc).

4. [Share a document](https://support.microsoft.com/office/share-your-documents-651e1cb9-9a51-46dc-8d32-bdb7d928eedd) with a team member.

<a name='start-using-the-microsoft-365-defender-portal-'></a>

## Start using the Microsoft Defender portal

1. Access the Microsoft Defender portal at <https://security.microsoft.com>.

2. Take some time to [familiarize yourself with the portal](/defender-business/mdb-get-started).

3. Now, [assess your security posture](/defender-xdr/microsoft-secure-score), and see how you can improve your score.

4. Learn how to [respond to a security incident](/defender-business/mdb-respond-mitigate-threats).

5. Lastly, [review remediation actions](/defender-business/mdb-review-remediation-actions).

## See also

- [Microsoft 365 Business Premium - cybersecurity for small business](m365bp-overview.md)
- [What is Microsoft Defender for Business?](/defender-business/mdb-overview)
