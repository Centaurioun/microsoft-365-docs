---
title: "Top 12 tasks for security teams to support working from home"
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: dansimp
audience: Admin
ms.topic: tutorial
ms.service: microsoft-365-security
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- m365-security
- remotework
- tier2
- trust-pod
ms.custom: admindeeplinkDEFENDER
description: "Protect your business email and data from cyber threats, including ransomware, phishing, and malicious attachments."
ms.date: 9/18/2023
---

# Top 12 tasks for security teams to support working from home

If you are like [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) and suddenly find yourself supporting a primarily home-based workforce, we want to help you ensure your organization is working as securely as possible. This article prioritizes tasks to help security teams implement the most important security capabilities as quickly as possible.

:::image type="content" source="../media/security/security-support-remote-work.png" alt-text="The top tasks to perform to support working from home" lightbox="../media/security/security-support-remote-work.png":::


If you're a small or medium-size organization using one of Microsoft's business plans, see these resources instead:

- [Best practices for securing Microsoft 365 for business plans](../business-premium/secure-your-business-data.md)
- [Microsoft 365 for Campaigns](../business-premium/m365bp-overview.md) (includes a recommended security configuration for Microsoft 365 Business)

For customers using our enterprise plans, Microsoft recommends you complete the tasks listed in the following table that apply to your service plan. Instead of purchasing a Microsoft 365 enterprise plan, if you're combining subscriptions, note the following items:

- Microsoft 365 E3 includes Enterprise Mobility + Security (EMS) E3 and Microsoft Entra ID P1
- Microsoft 365 E5 includes EMS E5 and Microsoft Entra ID P2

|Step|Task|All Office 365 Enterprise plans|Microsoft 365 E3|Microsoft 365 E5|
|---|---|---|---|---|
|1|[Enable Microsoft Entra multifactor authentication (MFA)](#1-enable-azure-ad-multifactor-authentication-mfa)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|2|[Protect against threats](#2-protect-against-threats)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|3|[Configure Microsoft Defender for Office 365](#3-configure-microsoft-defender-for-office-365)|||![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|4|[Configure Microsoft Defender for Identity](#4-configure-microsoft-defender-for-identity)|||![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|5|[Turn on Microsoft Defender XDR](#5-turn-on-microsoft-365-defender)|||![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|6|[Configure Intune mobile app protection for phones and tablets](#6-configure-intune-mobile-app-protection-for-phones-and-tablets)||![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|7|[Configure MFA and conditional access for guests, including Intune app protection](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)||![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|8|[Enroll PCs into device management and require compliant PCs](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)||![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|9|[Optimize your network for cloud connectivity](#9-optimize-your-network-for-cloud-connectivity)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|10|[Train users](#10-train-users)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|11|[Get started with Microsoft Defender for Cloud Apps](#11-get-started-with-microsoft-defender-for-cloud-apps)|||![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|
|12|[Monitor for threats and take action](#12-monitor-for-threats-and-take-action)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|![Included.](../media/d238e041-6854-4a78-9141-049224df0795.png)|

Before you begin, check your [Microsoft 365 Secure Score](./defender/microsoft-secure-score.md) in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft Defender portal</a>. From a centralized dashboard, you can monitor and improve the security for your Microsoft 365 identities, data, apps, devices, and infrastructure. You're given points for configuring recommended security features, performing security-related tasks (such as viewing reports), or addressing recommendations with a third-party application or software. The recommended tasks in this article will raise your score.

:::image type="content" source="../media/secure-score.png" alt-text="The Microsoft Secure Score screen in the Microsoft Defender portal" lightbox="../media/secure-score.png":::

<a name='1-enable-azure-ad-multifactor-authentication-mfa'></a>

## 1: Enable Microsoft Entra multifactor authentication (MFA)

The single best thing you can do to improve security for employees working from home is to turn on MFA. If you don't already have processes in place, treat this condition as an emergency pilot and make sure you have support folks ready to help employees who get stuck. As you probably can't distribute hardware security devices, use Windows Hello biometrics and smartphone authentication apps like Microsoft Authenticator.

Normally, Microsoft recommends you give users 14 days to register their device for multifactor authentication before requiring MFA. However, if your workforce is suddenly working from home, go ahead and require MFA as a security priority and be prepared to help users who need it.

Applying these policies takes only a few minutes, but be prepared to support your users over the next several days.

|Plan|Recommendation|
|---|---|
|Microsoft 365 plans (without Microsoft Entra ID P1 or P2)|[Enable Security defaults in Microsoft Entra ID](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Security defaults in Microsoft Entra ID include MFA for users and administrators.|
|Microsoft 365 E3 (with Microsoft Entra ID P1)|Use [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies: <ul><li>[Require MFA for administrators](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</li><li>[Require MFA for all users](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</li><li>[Block legacy authentication](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</li></ul>|
|Microsoft 365 E5 (with Microsoft Entra ID P2)|Taking advantage of feature in Microsoft Entra ID, begin to implement Microsoft's [recommended set of Conditional Access and related policies](./office-365-security/zero-trust-identity-device-access-policies-common.md) like: <ul><li>Requiring MFA when sign-in risk is medium or high.</li><li>Blocking clients that don't support modern authentication.</li><li>Requiring high risk users change their password.</li></ul>|

## 2: Protect against threats

All Microsoft 365 plans with cloud mailboxes include the following default email protection features:

- [Anti-malware](/defender-office-365/anti-malware-protection-about).
- [Anti-spam](/defender-office-365/anti-spam-protection-about).
- [Anti-spoofing](/defender-office-365/anti-phishing-policies-about#spoof-settings) in anti-phishing policies.

Default settings for these protection features are automatically assigned to all recipients via default policies. But, **to bump up the protection level to Microsoft's recommended Standard or Strict security settings based on observations in the datacenters, turn on and assign the Standard preset security policy (for most users) and/or the Strict preset security policy (for admins and other high-risk users)**. As new protection capabilities are added and as the security landscape changes, the settings in preset security policies are automatically updated to our recommended settings.

For instructions, see [Use the Microsoft Defender portal to assign Standard and Strict preset security policies to users](office-365-security/preset-security-policies.md#use-the-microsoft-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users).

The differences between Standard and Strict are summarized in the table [here](office-365-security/preset-security-policies.md#policy-settings-in-preset-security-policies). The comprehensive settings for Standard and Strict settings are described in the tables [here](office-365-security/recommended-settings-for-eop-and-office365.md#anti-spam-anti-malware-and-anti-phishing-protection-in-eop).

## 3: Configure Microsoft Defender for Office 365

Microsoft Defender for Office 365 (included with Microsoft 365 E5 and Office 365 E5) provides additional safeguards:

- [Safe Attachments](office-365-security/safe-attachments-about.md) and [Safe Links protection](office-365-security/safe-links-about.md): Protects your organization from unknown threats in real time by using intelligent systems that inspect files, attachments, and links for malicious content. These automated systems include a robust detonation platform, heuristics, and machine learning models.
- [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](office-365-security/safe-attachments-for-spo-odfb-teams-about.md): Protects your organization when users collaborate and share files, by identifying and blocking malicious files in team sites and document libraries.
- [Impersonation protection in anti-phishing policies](office-365-security/anti-phishing-policies-about.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365): Applies machine learning models and advanced impersonation-detection algorithms to avert phishing attacks.
- [Priority account protection](office-365-security/priority-accounts-turn-on-priority-account-protection.md): [Priority accounts](../admin/setup/priority-accounts.md) is a tag that you apply to a select number of high-value user accounts. Then, you can use the **Priority** tag as a filter in alerts, reports, and investigations. In Defender for Office 365 Plan 2 (included in Microsoft 365 E5), *priority account protection* offers additional heuristics for priority accounts that are tailored to company executives (regular employees don't benefit from this specialized protection).

For an overview of Defender for Office 365, including a summary of plans, see [Defender for Office 365](./office-365-security/defender-for-office-365.md).

The [Built-in protection preset security policy](office-365-security/preset-security-policies.md#profiles-in-preset-security-policies) gives Safe Links and Safe Attachments protection to all recipients by default, but you can [specify exceptions](office-365-security/preset-security-policies.md#use-the-microsoft-defender-portal-to-add-exclusions-to-the-built-in-protection-preset-security-policy).

As in the previous section, **to bump up the Defender for Office 365 protection level to Microsoft's recommended Standard or Strict security settings based on observations in the datacenters, turn on and assign the Standard preset security policy (for most users) and/or the Strict preset security policy (for admins and other high-risk users)**. As new protection capabilities are added and as the security landscape changes, the Defender for Office 365 settings in preset security policies are automatically updated to our recommended settings.

The users that you select for **Defender for Office 365 protection** in preset security policies get Microsoft's recommended Standard or Strict security settings for Safe Attachments and Safe Links. You also need to add entries and optional exceptions for [user impersonation and domain impersonation protection](office-365-security/anti-phishing-policies-about.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

For instructions, see [Use the Microsoft Defender portal to assign Standard and Strict preset security policies to users](office-365-security/preset-security-policies.md#use-the-microsoft-defender-portal-to-assign-standard-and-strict-preset-security-policies-to-users).

The differences between **Defender for Office 365 protection** settings in Standard and Strict are summarized in the table [here](office-365-security/preset-security-policies.md#policy-settings-in-preset-security-policies). The comprehensive settings for Standard and Strict **Defender for Office 365 protection** settings are described in the tables [here](office-365-security/recommended-settings-for-eop-and-office365.md#microsoft-defender-for-office-365-security). 

You can turn on and turn off Safe Attachments for SharePoint, OneDrive, and Microsoft Teams independently of preset security policies (it's on by default). To verify, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](office-365-security/safe-attachments-for-spo-odfb-teams-configure.md).

After you [identify users as priority accounts](../admin/setup/priority-accounts.md), they get priority account protection if it's turned on (it's on by default). To verify, see [Configure and review priority account protection in Microsoft Defender for Office 365](office-365-security/priority-accounts-turn-on-priority-account-protection.md).

## 4: Configure Microsoft Defender for Identity

[Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp) is a cloud-based security solution that uses on-premises Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization. Focus on this item next because it protects your on-premises and cloud infrastructure, has no dependencies or prerequisites, and can provide immediate benefit.

- See [Microsoft Defender for Identity Quickstarts](/azure-advanced-threat-protection/install-atp-step1) to get setup quickly
- Watch [Video: Introduction to Microsoft Defender for Identity](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Review the [three phases of Microsoft Defender for Identity deployment](/azure-advanced-threat-protection/what-is-atp#whats-next)

<a name='5-turn-on-microsoft-365-defender'></a>

## 5: Turn on Microsoft Defender XDR

Now that you have Microsoft Defender for Office 365 and Microsoft Defender for Identity configured, you can view the combined signals from these capabilities in one dashboard. [Microsoft Defender XDR](./defender/microsoft-365-defender.md) brings together alerts, incidents, automated investigation and response, and advanced hunting across workloads (Microsoft Defender for Identity, Defender for Office 365, Microsoft  Defender for Endpoint, and Microsoft Defender for Cloud Apps) into a single pane in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft Defender portal</a>.

:::image type="content" source="../media/top-ten-security-remote-work-mtp-dashboard.png" alt-text="The Microsoft Defender XDR dashboard" lightbox="../media/top-ten-security-remote-work-mtp-dashboard.png":::

After you configure one or more of your Defender for Office 365 services, turn on MTP. New features are added continually to MTP; consider opting in to receive preview features.

- [Learn more about MTP](./defender/microsoft-365-defender.md)
- [Turn on MTP](./defender/m365d-enable.md)
- [Opt in for preview features](./defender/preview.md)

## 6: Configure Intune mobile app protection for phones and tablets

Microsoft Intune Mobile Application Management (MAM) allows you to manage and protect your organization's data on phones and tablets without managing these devices. Here's how it works:

- You create an App Protection Policy (APP) that determines which apps on a device are managed and what behaviors are allowed (such as preventing data from a managed app from being copied to an unmanaged app). You create one policy for each platform (iOS, Android).
- After creating the app protection policies, you enforce these by creating a conditional access rule in Microsoft Entra ID to require approved apps and APP data protection.

APP protection policies include many settings. Fortunately, you don't need to learn about every setting and weigh the options. Microsoft makes it easy to apply a configuration of settings by recommending starting points. The [Data protection framework using app protection policies](/mem/intune/apps/app-protection-framework) includes three levels you can choose from.

Even better, Microsoft coordinates this app protection framework with a set of conditional access and related policies we recommend all organizations use as a starting point. If you implemented MFA using the guidance in this article, you're half way there!

To configure mobile app protection, use the guidance in [Common identity and device access policies](./office-365-security/zero-trust-identity-device-access-policies-common.md):

 1. Use the [Apply APP data protection policies](./office-365-security/zero-trust-identity-device-access-policies-common.md#app-protection-policies) guidance to create policies for iOS and Android. Level 2 (enhanced data protection) is recommended for baseline protection.
 2. Create a conditional access rule to [Require approved apps and APP protection](./office-365-security/zero-trust-identity-device-access-policies-common.md#require-approved-apps-and-app-protection-policies).

## 7: Configure MFA and conditional access for guests, including Intune mobile app protection

Next, let's ensure you can continue to collaborate and work with guests. If you're using the Microsoft 365 E3 plan and you implemented MFA for all users, you're set.

If you're using the Microsoft 365 E5 plan and you're taking advantage of Azure Identity Protection for risk-based MFA, you need to make a couple of adjustments (because Microsoft Entra ID Protection doesn't extend to guests):

- Create a new conditional access rule to require MFA always for guests and external users.
- Update the risk-based MFA conditional access rule to exclude guests and external users.

Use the guidance in [Updating the common policies to allow and protect guest and external access](./office-365-security/zero-trust-identity-device-access-policies-guest-access.md) to understand how guest access works with Microsoft Entra ID and to update the affected policies.

The Intune mobile app protection policies you created, together with the conditional access rule to require approved apps and APP protection, apply to guests accounts and help protect your organization's data.

> [!NOTE]
> If you already enrolled PCs into device management to require compliant PCs, you'll also need to exclude guest accounts from the conditional access rule that enforces device compliance.

## 8: Enroll PCs into device management and require compliant PCs

There are several methods to enroll your workforce's devices. Each method depends on the device's ownership (personal or corporate), device type (iOS, Windows, Android), and management requirements (resets, affinity, locking). This investigation can take a bit of time to sort out. See: [Enroll devices in Microsoft Intune](/mem/intune/enrollment/).

The quickest way to get going is to [Set up automatic enrollment for Windows 10 devices](/mem/intune/enrollment/quickstart-setup-auto-enrollment).

You can also take advantage of these tutorials:

- [Use Autopilot to enroll Windows devices in Intune](/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Use Apple's Corporate Device Enrollment features in Apple Business Manager (ABM) to enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

After enrolling devices, use the guidance in [Common identity and device access policies](./office-365-security/zero-trust-identity-device-access-policies-common.md) to create these policies:

- [Define device-compliance policies](./office-365-security/zero-trust-identity-device-access-policies-common.md#create-device-compliance-policies): The recommended settings for Windows 10 include requiring antivirus protection. If you have Microsoft 365 E5, use Microsoft Defender for Endpoint to monitor the health of employee devices. Be sure compliance policies for other operating systems include antivirus protection and end-point protection software.
- [Require compliant PCs](./office-365-security/zero-trust-identity-device-access-policies-common.md#require-compliant-pcs-and-mobile-devices): This is the conditional access rule in Microsoft Entra ID that enforces the device compliance policies.

Only one organization can manage a device, so be sure to exclude guest accounts from the conditional access rule in Microsoft Entra ID. If you don't exclude guest and external users from policies that require device compliance, these policies will block these users. For more information, see [Updating the common policies to allow and protect guest and external access](./office-365-security/zero-trust-identity-device-access-policies-guest-access.md).

## 9: Optimize your network for cloud connectivity

If you're rapidly enabling the bulk of your employees to work from home, this sudden switch of connectivity patterns can have a significant impact on the corporate network infrastructure. Many networks were scaled and designed before cloud services were adopted. In many cases, networks are tolerant of remote workers, but weren't designed to be used remotely by all users simultaneously.

Network elements are suddenly put under enormous strain due to the load of the entire business using them. For example:

- VPN concentrators.
- Central network egress equipment (such as proxies and data loss prevention devices).
- Central internet bandwidth.
- Backhaul MPLS circuits
- NAT capability.

The end result is poor performance and productivity coupled with a poor experience for users who are adapting to working from home.

Some of the protections that have traditionally been provided by routing traffic back through a corporate network are now provided by the cloud apps that your users are accessing. If you reach this step in this article, you've implemented a set of sophisticated cloud security controls for Microsoft 365 services and data. With these controls in place, you may be ready to route remote users' traffic directly to Office 365. If you still require a VPN link for access to other applications, you can greatly improve your performance and user experience by implementing split tunneling. Once you achieve agreement in your organization, this optimization can be accomplished within a day by a well-coordinated network team.

For more information, see:

- [Overview: Optimize connectivity for remote users using VPN split tunneling](/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Implementing VPN split tunneling for Office 365](/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Recent blog articles on this topic:

- [How to quickly optimize traffic for remote staff & reduce the load on your infrastructure](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Alternative ways for security professionals and IT to achieve modern security controls in today's unique remote work scenarios](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

## 10: Train users

Training users can save your users and security operations team a lot of time and frustration. Savvy users are less likely to open attachments or click links in questionable email messages, and they're more likely to avoid suspicious websites.

The Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/p/?linkid=2015598) provides excellent guidance on establishing a strong culture of security awareness within your organization, including training users to identify phishing attacks.

Microsoft 365 provides the following resources to help inform users in your organization:

|Concept|Resources|
|---|---|
|Microsoft 365|[Customizable learning pathways](/office365/customlearning/) <p>These resources can help you put together training for end users in your organization|
|Microsoft 365 security|[Learning module: Secure your organization with built-in, intelligent security from Microsoft 365](/training/modules/security-with-microsoft-365) <p>This module enables you to describe how Microsoft 365 security features work together and to articulate the benefits of these security features.|
|Multifactor authentication|[Two-step verification: What is the additional verification page?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>This article helps end users understand what multifactor authentication is and why it's being used at your organization.|

In addition to this guidance, Microsoft recommends that your users take the actions described in this article: [The keys to the kingdom - securing your devices and accounts](https://support.microsoft.com/office/a925f8ad-af7e-40d8-9ce4-60ea1cac2ba4). These actions include:

- Using strong passwords
- Protecting devices
- Enabling security features on Windows 10 and Mac PCs (for unmanaged devices)

Microsoft also recommends that users protect their personal email accounts by taking the actions recommended in the following articles:

- [Help protect your Outlook.com email account](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [Protect your Gmail account with 2-step verification](https://go.microsoft.com/fwlink/p/?linkid=2015688)

## 11: Get started with Microsoft Defender for Cloud Apps

[Microsoft Defender for Cloud Apps](/cloud-app-security) provides rich visibility, control over data travel, and sophisticated analytics to identify and combat cyberthreats across all your cloud services. Once you get started with Defender for Cloud Apps, anomaly detection policies are automatically enabled. But, Defender for Cloud Apps has an initial learning period of seven days during which not all anomaly detection alerts are raised.

Get started with Defender for Cloud Apps now. Later you can set up more sophisticated monitoring and controls.

- [Quickstart: Get started with Defender for Cloud Apps](/cloud-app-security/getting-started-with-cloud-app-security)
- [Get instantaneous behavioral analytics and anomaly detection](/cloud-app-security/anomaly-detection-policy)
- [Learn more about Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)
- [Review new features and capabilities](/cloud-app-security/release-notes)
- [See basic setup instructions](/cloud-app-security/general-setup)

## 12: Monitor for threats and take action

Microsoft 365 includes several ways to monitor status and take appropriate actions. Your best starting point is the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft Defender portal</a>, where you can view your organization's [Microsoft Secure Score](./defender/microsoft-secure-score.md), and any alerts or entities that require your attention.

- [Get started with the Microsoft Defender portal](./defender/microsoft-365-defender-portal.md)
- [See the security portals in Microsoft 365](./defender/portals.md)

## Next steps

Congratulations! You've quickly implemented some of the most important security protections and your organization is much more secure. Now you're ready to go even further with threat protection capabilities (including Microsoft Defender for Endpoint), data classification and protection capabilities, and securing administrative accounts. For a deeper, methodical set of security recommendations for Microsoft 365, see [Microsoft 365 Security for Business Decision Makers (BDMs)](Microsoft-365-security-for-bdm.md).

Also visit Microsoft's new Defender for Cloud in [Security documentation](/security).
