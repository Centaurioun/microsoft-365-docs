---
title: "Step 1. Increase sign-in security for hybrid workers with MFA"
f1.keywords:
- NOCSH
author: brendacarter
ms.author: bcarter
manager: dansimp
ms.date: 05/01/2020
audience: ITPro
ms.topic: how-to
ms.service: o365-solutions
ms.localizationpriority: high
ms.collection: 
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: 
description: Require that your hybrid workers sign in with multifactor authentication (MFA).
---

# Step 1. Increase sign-in security for hybrid workers with MFA

To increase the security of sign-ins of your hybrid workers, use multifactor authentication (MFA). MFA requires that user sign-ins be subject to an additional verification beyond the user account password. Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.

![The correct password plus an additional verification results in a successful sign-in.](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

For all users, including hybrid workers and especially admins, Microsoft strongly recommends MFA.

There are three ways to require your users to use MFA based on your Microsoft 365 plan.

|Plan  |Recommendation  |
|---------|---------|
|All Microsoft 365 plans (without Microsoft Entra ID P1 or P2 licenses)     |[Enable Security defaults in Microsoft Entra ID](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Security defaults in Microsoft Entra ID include MFA for users and administrators.   |
|Microsoft 365 E3 (includes Microsoft Entra ID P1 licenses)     | Use [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies: <br>- [Require MFA for administrators](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Require MFA for all users](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Block legacy authentication](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (includes Microsoft Entra ID P2 licenses)     |Taking advantage of feature in Microsoft Entra ID, begin to implement Microsoft's [recommended set of Conditional Access and related policies](../security/office-365-security/zero-trust-identity-device-access-policies-common.md) like:<br/> - Requiring MFA when sign-in risk is medium or high. <br/>- Blocking clients that don't support modern authentication. <br/>- Requiring high risk users change their password.|

## Security defaults

Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019. These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.
 
Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled. After 14 days have passed, the user won't be able to sign in until MFA registration is completed.

Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default. You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.

For more information, see this [overview of security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).

## Conditional Access policies

Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed. For example, you can create a Conditional Access policy that states:

- If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.

This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.

You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 11 or 10.

Conditional Access requires Microsoft Entra ID P1 licenses, which are included with Microsoft 365 E3 and E5.

For more information, see this [overview of Conditional Access](/azure/active-directory/conditional-access/overview).

<a name='azure-ad-identity-protection-support'></a>

## Microsoft Entra ID Protection support

With Microsoft Entra ID Protection, you can create an additional Conditional Access policy that states:

- If the risk of the sign-in is determined to be medium or high, require MFA.

Microsoft Entra ID Protection requires Microsoft Entra ID P2 licenses, which are included with Microsoft 365 E5.

For more information, see [Risk-based Conditional Access](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users).

With Microsoft Entra ID Protection, you can also create a policy to require your users to register for MFA. For more information, see [Configure the Microsoft Entra multifactor authentication registration policy](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)


## Using these methods together

Keep the following in mind:

- You cannot enable security defaults if you have any Conditional Access policies enabled.
- You cannot enable any Conditional Access policies if you have security defaults enabled.

If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app. 

This table shows the results of enabling MFA with security defaults and Conditional Access policies.

| Method | Enabled | Disabled | Additional authentication method |
|:-------|:-----|:-------|:-------|
| **Security defaults**  | Can’t use Conditional Access policies | Can use Conditional Access policies | Microsoft Authenticator app |
| **Conditional Access policies** | If any are enabled, you can’t enable security defaults | If all are disabled, you can enable security defaults  | User specifies during MFA registration  |
||||

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. For more information, see [Plan a Microsoft Entra self-service password reset deployment](/azure/active-directory/authentication/howto-sspr-deployment).

<a name='sign-in-to-saas-apps-with-azure-ad'></a>

## Sign in to SaaS apps with Microsoft Entra ID

In addition to providing cloud authentication for users, Microsoft Entra ID can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Microsoft Entra ID](/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for hybrid workers to discover the applications they need and sign into them securely.

## Admin technical resources for MFA and identity

- [Top 5 ways your Microsoft Entra ID can help you enable remote work](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [Identity infrastructure for Microsoft 365](../enterprise/deploy-identity-solution-overview.md)
- [Azure Academy Microsoft Entra ID training videos](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## Results of Step 1

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

## Next step

[![Step 2: Provide remote access to on-premises apps and services.](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)

Continue with [Step 2](empower-people-to-work-remotely-remote-access.md) to provide remote access to on-premises apps and services.
