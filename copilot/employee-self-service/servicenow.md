---
title: Integrate ServiceNow with your Employee Self-Service deployment
f1.keywords: NOCSH
ms.author: daisyfeller
author: daisyfell
manager: triciagill
ms.date: 6/20/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.custom: ess-agent
ms.localizationpriority: medium
ms.collection: m365copilot
description: Learn about integrating ServiceNow in the deployment process for the Employee Self-Service agent.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Integrate ServiceNow with your Employee Self-Service deployment

ESS Agent being a new capability built by Microsoft that runs on top of Copilot applying Artificial Intelligence (AI) in providing relevant information to employees and taking actions on their HR data.

As most organizations manage HR data in an HCM & Knowledge base system, ESS Agent should have access to this data on behalf of users. With ServiceNow being one of the Knowledge base systems, this document helps set up the ESS Agent integration with ServiceNow Knowledge base using Knowledge Graph Connector.

ESS Agent continues to serve as unified assistants for employees to provide knowledge services and connecting with ServiceNow makes it truly an enterprise HR/IT assistant.

## Functional Synopsis 

ESS Agent acts as a front-end for consuming information from ServiceNow Knowledge using the Microsoft Graph Connector and following are the capabilities that’s enabled for this integration:

- Employees can ask questions related to IT/HR workflows
    - How do I request a new device? 
    - How to create a new VPN connection?
    - How do I apply for leave? 
- Use Semantic search in ESS Agent to enable employees to find relevant content based on keywords, personal preferences and social connections
- Employees can search for knowledge-based articles in ESS Agent after it’s indexed and visible to all users or restricted with user criteria permissions

## Technical Synopsis

:::image type="content" source="media/service-now-integration.png" alt-text="Diagram that shows the high-level components comprising overall solution for ESS Agent and ServiceNow Knowledge integration." lightbox="media/service-now-integration.png":::

The preceding diagram outlines the high-level components comprising overall solution for ESS Agent and ServiceNow Knowledge integration using Microsoft Graph Connector. There are different activities to be performed as part of initial deployment and for an ongoing operation. As the solution involves multiple technologies, it’s better to spend some time initially in understanding the various components and bring in the right stakeholders to set 
up an environment to deploy and test ESS Agent.

> [!NOTE]
> ServiceNow Knowledge Microsoft Graph Connector (GC) is still a preview version, which means the current implementation that’s documented here might have few limitations, known issues and change in the future release targeted for General Availability (GA).

## Prerequisites

- ServiceNow Knowledge instance 
- Microsoft 365 Tenant 

For information on subscription requirements required for the ESS Agent itself, see the ESS Agent deployment guide.

## Limitations

The current version of ServiceNow Knowledge Microsoft Graph Connector is a prerelease version and have the following limitations:

- No support for “Advanced Scripts”. For more information, see [ServiceNow documentation](https://www.servicenow.com/docs/bundle/xanadu-servicenow-platform/page/product/knowledge-management/task/create-user-criteria-record-in-knowledge-management.html) for Advanced Scripts – the current version have a workaround via scripted APIs, work with your Microsoft Product/Program Manager for further support on this.
- If both Knowledge base and Knowledge article level permissions are defined, then only article-level permissions are honored (no support for hierarchical permissions).
- Attachments aren't indexed.

## Deployment role requirements

|Roles/Persona  |Description  |Activities performed  |Configuration areas  |
|---------|---------|---------|---------|
|ServiceNow Administrator     |User who can perform administrative tasks         |Create a service account and assign a role to provide read access to specific table records         |ServiceNow         |
|ServiceNow     |User who can configure access control         |1. Create OAuth Application Registry<br> Following steps are required only if “Advanced Scripts” are in place:<br> 2. Configure Access Control (ACL) for REST endpoint.<br>3. Create scripted REST API.<br>4. Define the API Resource.         |ServiceNow         |
|Global Administrator (or) Search Administrator     |User who can configure the Microsoft Graph Connector for ServiceNow Knowledge.         |`1. Establish a Microsoft Enterprise Application.<br>2. Configure SAML settings within the Enterprise Application.<br>3. Obtain the Enterprise Application’s SAML certificate.<br>4. Establish trust.         |Microsoft 365 Admin Center         |
|Environment Maker     |User who can customize ESS Agent.         |Configure knowledge source using ServiceNow Knowledge Microsoft Graph Connector.         |Microsoft Copilot Studio         |

## ServiceNow Configuration

This section outlines the tasks required to be configured in ServiceNow by an administrator. ServiceNow integration supports 3 types of authentications as follows:

1. Basic authentication – recommended if Advanced Script is used
1. ServiceNow OAuth (recommended) – this is covered in this article
1. Microsoft Entra ID OpenID Connect

> [!NOTE]
> For all security related tasks in ServiceNow, the signed-in user with admin or security_admin role must elevate their access using “Elevate role” option from the profile menu in the top-right of navigation bar.

Without elevating access, the new security objects can't be created. If **New** button in the top right of configuration pane is missing, then the role isn't elevated to "*security_admin*".

## Task 1: Create an OAuth Application Registry (recommended)

1. Sign in to the ServiceNow instance that needs to be integrated with ESS Agent.
1. Elevate access permissions using **Elevate role**.
1. Select **All** in the top navigation bar.
1. Search for **OAuth** in the search box within dropdown navigation menu.
1. Select “System OAuth → Application Registry” from the search results (if you don’t see this option, then you don’t have sufficient privileges).
1. Select **New** in the top right-corner of the configuration section pane.
1. Select **Create an OAuth API endpoint for external clients**.
1. Fill in the following information for the new application registry:

   |Configuration  |Description  |
   |---------|---------|
   |Name    |A meaningful name to identify that this application registry is created for ESS Agent.          |
   |Client ID      |Autogenerated code.<br> **Note**: This value is used in Microsoft Graph Connector configuration if no Advanced Scripting is used.         |
   |Client Secret      |Leave it blank for a string to be automatically generated.<br> **Note**: This value is used in Microsoft Graph Connector configuration if no Advanced Scripting is used.          |
   |Row4Redirect URL     |A required callback URL that the authorization server redirects to:<br> **For M365 Enterprise**: `https://gcs.office.com/v1.0/admin/oauth/callback`<br> **For M365 Government**: `https://gcsgcc.office.com v1.0/admin/oauth/callback`         |
   |Active      |Set to active.         |
   |Refresh token lifespan       |The number of seconds that a refresh token is valid. By default, refresh tokens expire in 100 days (8,640,000 seconds).  Recommended value is 31,536,000 (one year).          |
   |Access token lifespan       |The number of seconds that an access token is valid. Recommended value is 43,200 (12 hours).         |
   |Application      |Global.         |
   |Accessible from      |All application scopes.         |
   |Client Type      |Integration as a Service.         |

1. Select **Submit** or **Update** button to save the changes.

This is the only configuration needed on ServiceNow for integrating with Microsoft Graph Connector without Advanced Scripts.

The following tasks are required ONLY if Advanced Scripts are used in ServiceNow for controlling access to knowledge bases and articles using user criteria:

## Task 2: Configure Access Control for REST endpoint

This task is required to ensure only the crawling account can access the REST API.

1. Sign in to the ServiceNow instance that needs to be integrated with ESS Agent.
1. Elevate access permissions using **Elevate role**.
1. Select **All** in the top navigation bar.
1. Search for **Access Control** in the search box within dropdown navigation menu.
1. Select **System Security** → **Access Control (ACL)**” from the search results.
1. Select **New** in the top-right corner of configuration section pane 
1. In the new form, fill in the following information.

   |Configuration  |Description/Value  |
   |---------|---------|
   |Type     |Type of object to be secured with this ACL; select **REST_Endpoint**.         |
   |Application     |Global         |
   |Operation     |Execute         |
   |Decision Type     |Allow If         |
   |Admin overrides      |Checked         |
   |Name     |Provide a meaningful name to identify the purpose of this ACL, for example, “Microsoft Copilot”.          |
   |Description     |Provide a relevant description         |
   |Active     |Checked         |
   |Role     |An account which is used to crawl the content.<br> **Note**: This is the account that should be used for Microsoft Graph Connector configuration with Basic authentication.         |

1. Select **Submit** to save changes.

## Task 3: Create scripted REST API

This task is required to define a custom script processing for user criteria.

1. Sign in to the ServiceNow instance that needs to be integrated with ESS Agent.
1. Elevate access permissions using **Elevate role**.
1. Select **All** in the top navigation bar.
1. Search for **Scripted REST** in the search box within dropdown navigation menu.
1. Select **System Web Services** → **Scripted Web Services** → **Scripted REST APIs** from the search results.
1. Fill in the following configuration information.

   |Configuration  |Description/Value  |
   |---------|---------|
   |Name     |Provide a name that identifies the purpose.         |
   |API ID    |Auto generated         |
   |API namespace     |Auto generated<br> **Note**: This value is used in Microsoft Graph Connector configuration.         |

1. Select **Submit** to save changes.
1. Click on the newly created Scripted REST API from the list.
1. Under the **Security** tab, select **Default ACLs**.
1. Remove the default value and add/look up the ACL that’s created in [Task 2: Configure Access Control for REST endpoint](#task-2-configure-access-control-for-rest-endpoint).
1. Add the ACL and update the changes.

## Task 4: Define the API resource

This task is required to define the custom script as a resource for the REST API that’s created in the previous task

1. From the **Scripted REST API** list, select the one that’s created in [Task 3](#task-2-configure-access-control-for-rest-endpoint).
2. At the bottom of the page, select the **Resources** tab and select **New**. 
3. Fill in the following configuration.

   |Configuration  |Description/Value  |
   |---------|---------|
   |Name     |GetAllUserCriteria          |
   |Relative path     |/user_criteria         |
   |Script     |Copy and paste the following script AS IS:<br> (function execute (/*RESTAPIRequest*/ request,<br>/*RESTAPIResponse*/ response)<br>{<br>var queryParams = request.queryParams;<br>var user = new String(queryParams.user);<br>return (new<br>sn_uc.UserCriteriaLoader()).getAllUserCriteria(user);<br>}<br>)(request, response);         |
   |Requires authentication     |Checked         |
   |Requires ACL authorization     |Checked<br>Ensure that the ACL created in Task 2 is set correctly and remove any other default values.          |

4. Select **Submit** to save changes.

This wraps up all the configuration required on the ServiceNow side, now the next set of tasks are on Microsoft 365 side.

## Microsoft Graph Connector Configuration

This section covers the tasks required for configuring Microsoft Graph Connector in Microsoft Admin Center (MAC). These set of tasks requires a Global Admin role or a Security Admin role in Microsoft 365 tenant.

1. Sign in to the **Microsoft Admin Center**.
2. Select **Settings** → **Search & intelligence** in the left navigation pane.
3. In the **Search & intelligence** page, select **Data sources**.
4. Click **+ Add Connection** to add a new Graph connection.
5. In the **Connect to data source** page, from the list of connectors, search for **ServiceNow Knowledge**”
6. Select **ServiceNow Knowledge** connector and select**Next**.
7. Fill in the following configuration information:

   |Configuration  |Description/Value  |
   |---------|---------|
   |Display Name     |Provide a display name that helps to identify this connector within Copilot Studio by the Environment Makers for ESS Agent.         |
   |User Criteria Setup in ServiceNow     |Select **Simple** if no Advanced Scripting is setup; otherwise select **Advanced**.         |
   |ServiceNow instance     |Provide the ServiceNow instance name, which typically is https://organization name.service-now.com.         |
   |Authentication type     |Select **Basic** authentication for **Advanced Scripting** mode to use the service account configured in [Task 2: Configure Access Control for REST endpoint](#task-2-configure-access-control-for-rest-endpoint). Select **OAuth 2.0** authentication if no Advanced Scripting is used in ServiceNow (Simple), and use the Client ID and Client secret created in [Task 1: Create an OAuth Application Registry (recommended)](#task-1-create-an-oauth-application-registry-recommended).         |
   |API namespace     |Enter the API namespace for Scripted REST API created in [Task 3: Create scripted REST API](#task-3-create-scripted-rest-api).         |

8. Select **Authorize** once a desired authentication type is chosen based on the guidance provided in the table in [Deployment role requirements](#deployment-role-requirements) and the respective values are given.
9. Microsoft Graph Connector connects to the ServiceNow REST API to get authorized and ask for a consent to allow the authorization; select **Allow** for it. 
   When the authorization is successfully completed, the authorization fields will have a green check
10. Choose to enable or disable **_rollout to limited audience_** for staged rollout of this graph connector so that it can be tested with limited set of users before it’s rolled out to the whole organization.
11. Check **Notice** checkbox to authorize Microsoft to create an index of third-party data in Microsoft 365 tenant subject to the configurations.
12. Create **Create** to create the connector.
13. In the status page, it’ll show the connection status as either a **Success** or **Failure** message. A sync will be triggered in the background and its status will also be indicated.
14. Provide a description for the Connector which will serve as an instruction to Copilot and select **Save**.
15. Select **Done** and wait for the connection state to be **Ready** after the sync is completed.

## ESS Agent Configuration

This section outlines the steps to configure the newly created Microsoft Graph Connector above within ESS Agent as a knowledge source.

1. Sign in to Copilot Studio as an Environment Maker (https://copilotstudio.microsoft.com).
2. Open **ESS Agent**.
3. Select **Knowledge** from the top-navigation pane and select **+ Add Knowledge**.
4. Select **ServiceNow** from the list of connector options shown in the **Add knowledge** dialog box.
5. In the **Select ServiceNow connection** dialog box, it will list all the ServiceNow connections available within the current Copilot Studio environment, including the ones created by the tenant admins, which should show the Microsoft Graph Connection created in the previous section, under **Created by your admin** section.
6. Select the connector what has been created in [Microsoft Graph Connector Configuration](#microsoft-graph-connector-configuration)
7. Select **Add** to complete the configuration.
8. Confirm the newly created connector is in **Ready** state in the Microsoft Admin Center before the connector is being used in the agent.
9. Once the connector is ready, validate the connection by asking relevant queries in the Copilot Studio maker experience in the **Test** panel.
10. See the *Troubleshooting* section in the Appendix below for any issues encountered.

## APPENDIX

### Troubleshooting

[ServiceNow Knowledge Microsoft Graph connector](/microsoftsearch/servicenow-knowledge-connector) – Troubleshooting section References

For Custom Setup and complete configuration documentation, see:

- [ServiceNow Knowledge Microsoft Graph connector](/microsoftsearch/servicenow-knowledge-connector)

- [Semantic indexing for Microsoft 365 Copilot](/microsoftsearch/semantic-index-for-copilot)

- [Staged rollout for Microsoft Graph connectors](/MicrosoftSearch/staged-rollout-for-graph-connectors)

- [Map your non-Azure AD Identities](/MicrosoftSearch/map-non-aad)

- [Guidelines for Sync settings](/MicrosoftSearch/configure-connector)

For ServiceNow Knowledge documentation, see the following resources which require ServiceNow sign ins:

- [ServiceNow Knowledge – Advanced Scripts](https://docs.servicenow.com/bundle/xanadu-servicenow-platform/page/product/knowledge-management/task/create-user-criteria-record-in-knowledge-management.html)

- [Assign a role to a user](https://www.servicenow.com/docs/bundle/xanadu-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

- [Creating and Editing Access Controls](https://developer.servicenow.com/dev.do#!/learn/learning-plans/xanadu/new_to_servicenow/app_store_learnv2_securingapps_xanadu_creating_and_editing_access_controls)

- [Generate an encoded query string through a filter](https://www.servicenow.com/docs/bundle/xanadu-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html?state=seamless)

