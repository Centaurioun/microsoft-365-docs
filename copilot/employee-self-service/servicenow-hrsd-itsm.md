---
title: Integrate ServiceNow HRSD and ITSM with your Employee Self-Service deployment
f1.keywords: NOCSH
ms.author: daisyfeller
author: daisyfell
manager: triciagill
ms.date: 7/3/2025
audience: Admin
ms.topic: article
ms.service: microsoft-365-copilot
ms.custom: ess-agent
robots: NOINDEX, NOFOLLOW
ms.localizationpriority: medium
ms.collection: m365copilot
description: Learn about integrating ServiceNow HRSD and ITSM in the deployment process for the Employee Self-Service agent.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Integrate ServiceNow HRSD and ITSM with your Employee Self-Service deployment

>[!NOTE]
>The Employee Self-Service agent is currently in on-demand preview. Deployment processes are subject to change before this product becomes generally available.

>[!IMPORTANT]
>You need to complete the steps to deploy the Employee Self-Service (ESS) agent before you can configure this supplemental extension pack.

The Employee Self-Service agent is built on Copilot and uses AI to provide relevant information to employees and take actions on their HR data. If your organization uses a human resource management system, the ESS agent requires access to that system to function most effectively.

## Functional synopsis

ESS Agent acts as a front-end for consuming information from ServiceNow HRSD + ITSM using the Power Platform connector and following are the capabilities that’s enabled for this integration:

- Create an HR case
- Get case details
- Get case updates
- Get user cases
- Get ticket status
- Get ticket details
- Get ticket list
- Create ticket
- Update ticket

## Technical synopsis

:::image type="content" source="media/agent-service-now-integration.png" alt-text="Diagram the high-level components comprising overall solution for ESS agent and ServiceNow HRSD integration." lightbox="media/agent-service-now-integration.png":::

The previous diagram outlines the high-level components comprising overall solution for ESS agent and ServiceNow HRSD integration. There are different activities to be performed as a part of initial deployment and for an ongoing operation. As the solution involves multiple technologies, it’s better to spend some time initially in understanding the various components and bring in the right stakeholders to set up an environment to deploy and test ESS Agent.

## Known issues & limitations

The following are known issues & limitations of the Power Platform connector for ServiceNow:

- When using the Create Record action, it's not possible to specify the full record description. The field value is ignored due to ServiceNow REST API limitations.
- The Get Records action may return an "Invalid Table" or other error in Power Apps. For Power Apps implementations the suggested work-around is to utilize the Get Records action in Power Automate and pass the data back to Power Apps.

For detailed documentation about the connector, see [ServiceNow - Connectors](/connectors/service-now/#known-issues-and-limitations).

## Prerequisites

- ServiceNow HRSD / ITSM instance
- Microsoft 365 Tenant
- ESS Agent is installed

Refer to the ESS Agent deployment guide for installation of the agent and subscription requirements required for the ESS Agent itself.

### Deployment role requirements

| Roles / Persona | Description | Activities performed | Configuration Areas |
|---------|---------|---------|---------|
| **ServiceNow Administrator** | User who can perform administrative tasks | Create a service account and assign a role to provide read access to specific table records | ServiceNow |
| **ServiceNow Security Administrator** | User who can configure OAuth | Create OAuth Application Registry – *if using OAuth for ServiceNow connector* | ServiceNow |
| **Application Developer** (*minimum privileged role*)  | User who can register an application | Create an App registration - *if using Microsoft Entra OAuth for ServiceNow connector* | Microsoft 365 Admin Center |
| **Environment Maker** | User who can customize ESS Agent | Configure & Customize ESS Agent | Microsoft Copilot Studio |

### ServiceNow configuration

This section outlines the tasks required to be configured in ServiceNow by an administrator.  ServiceNow integration supports three types of authentications as follows:

1. Basic authentication
2. Microsoft Entra ID OAuth using certificate
3. Microsoft Entra ID User sign in
4. User Oauth2

> [!NOTE]
> For all security related tasks in ServiceNow, the logged in user with `admin` or `security_admin` role must elevate their access using "Elevate role" option from the profile menu in the top right of navigation bar.

> [!TIP]
> Without elevating access, the new security objects can't be created. If **New** button in the top right of configuration pane is missing, then the role isn't elevated to "`security_admin`”.

#### Option 1: Using OAuth2 authentication - Create an OAuth Application Registry

1. Log in to the ServiceNow instance that needs to be integrated with ESS Agent.
2. Elevate access permissions using **Elevate role**.
3. Select **All** in the top navigation bar.
4. Search for **OAuth** in the search box within dropdown navigation menu.
5. Select **System OAuth → Application Registry** from the search results (if you don’t see this option, then you don’t have sufficient privileges).
6. Select **New** button in the top right corner of the configuration section pane.
7. Select **Create an OAuth API endpoint for external clients**.
8. Fill in the following information for the new application registry:

    | Configuration | Description |
    |---------|---------|
    | **Name** | a meaningful name to identify that this application registry is created for ESS Agent |
    | **Client ID** | autogenerated code <br><div class="alert">**Note**</br>This value is used in Microsoft 365 Copilot Connector configuration, if no Advanced Scripting is used. |
    | **Client Secret** | leave it blank to automatically generate a string <br><div class="alert">**Note**</br>This value is used in Microsoft 365 Copilot Connector configuration, if no Advanced Scripting is used. |
    | **Redirect URL** | a required callback URL that the authorization server redirects to </br>For Microsoft 365 Enterprise:</br>`https://gcs.office.com/v1.0/admin/oauth/callback`</br>For Microsoft 365 Government:</br>`https://gcsgcc.office.com/v1.0/admin/oauth/callback`|
    | **Logo URL** | A URL that contains the image for the application logo |
    | **Active** | Set to active |
    | **Refresh token lifespan** | The number of seconds that a refresh token is valid. </br>By default, refresh tokens expire in 100 days (8,640,000 seconds). Recommended value is 31,536,000 (one year) |
    | **Access token lifespan** | The number of seconds that an access token is valid.</br> Recommended value is 43,200 (12 hours) |
    | **Application** | Global |
    | **Accessible from** | All application scopes |
    | **Client Type** | Integration as a Service |

9. Select **Submit** or **Update** button to save the changes.

### Install ServiceNow HRSD extension pack

ESS Agent is designed to have separate extension packs for each third party ISVs like ServiceNow, etc. Hence, these extension packs must be installed first before starting any configurations or customizations.
The following steps are required to install & enable the ServiceNow HRSD extension pack:

1. **Entitlement**
    Work with your ESS Agent private preview product managers for the entitlement process. Once the entitlement process is complete for your tenant, the ServiceNow HRSD extension pack shows up under "Customize" section of ESS Agent.

    > [!NOTE]
    > "Entitlement" process is a preview workaround until the extension pack installation is streamlined in Microsoft Copilot Studio.

2. **Open the ESS Agent in Copilot Studio**
    1. Open the ESS Agent in Copilot Studio.
    2. Navigate to **Settings**.
    3. Select **Customize** from the left navigation under **Settings**.
    4. Select **Employee Self-Service Agent in Microsoft 365 Copilot – ServiceNow HR Service Delivery** and select **Install**.
    5. When prompted, update the connections as described by selecting " ..." or **sign in** buttons on the right hand side for ServiceNow connection.
    6. Use the following parameters to complete the configuration (**if using OAuth2**):

        | Feature | Description |
        |---------|---------|
        | **Authentication Type** | Use Oauth2 |
        | **Instance Name** | The instance name used to identify the ServiceNow Site URl <br>For example:</br>**contoso** – *don't use the full url or domain name like contoso.service-now.com* |
        | **Client Id** | Client ID created in Task 1 |
        | **Client Secret** | Client ID created in Task 1 |

    7. ServiceNow asks for sign-in again. Use the same account used previously for ServiceNow configuration.
    8. Confirm the consent by selecting **Allow**.
    9. The **Microsoft Dataverse** connection is the user account that should be automatically signed in, if not, select **Sign in**.

### Install ServiceNow ITSM extension pack

ESS Agent is designed to have separate extension packs for each third party ISVs like ServiceNow, etc. Hence, these extension packs must be installed first before starting any configurations or customizations.
Following are the steps required to install & enable the ServiceNow HRSD extension pack:

1. **Entitlement**
    Please work with your ESS Agent private preview product managers for the entitlement process. Once the entitlement process is complete for your tenant, the ServiceNow HRSD extension pack shows up under "Customize" section of ESS Agent.

    > [!NOTE]
    > "Entitlement" process is a preview workaround until the extension pack installation is streamlined in Microsoft Copilot Studio.

2. **Install the extension**

    1. Open the ESS Agent in Copilot Studio.
    2. Navigate to **Settings**.
    3. Select **Customize** from the left navigation under **Settings**.
    4. Select **Employee Self-Service Agent in Microsoft 365 Copilot – ServiceNow IT Service Management** and select **Install**.
    5. When prompted, update the connections as described by selecting " ..." or **sign in** buttons on the right hand side for ServiceNow connection.
    6. Use the following parameters to complete the configuration (if using OAuth2):

        | Feature | Description |
        |---------|---------|
        | **Authentication Type** | Use Oauth2 |
        | **Instance Name** | The instance name used to identify the ServiceNow Site URl <br>For example:</br>**contoso** – *don't use the full url or domain name like contoso.service-now.com* |
        | **Client Id** | Client ID created in Task 1 |
        | **Client Secret** | Client ID created in Task 1 |

    7. ServiceNow asks for sign-in again. Use the same account used previously for ServiceNow configuration.
    8. Confirm the consent by selecting **Allow**.

## ServiceNow - HRSD

### Topics

The following Topics are available from the ServiceNow HRSD extension pack:

| Serial no. | Topics | Description |
|---------|---------|---------|
| 1 | **ServiceNow HRSD Create Case** | Creating an HR case in ServiceNow. |
| 2 | **ServiceNow HRSD System Create Case** | This topic isn't an editable topic. Create case calls this for further processing.  |
| 3 | **ServiceNow HRSD Get Case Details** | Gets latest created case details. |
| 4 | **ServiceNow HRSD System Get Case Details** | This topic isn't an editable topic. Get case details calls this for further processing. |
| 5 | **ServiceNow HRSD Get Case Updates** | Get case update details in text format.</br> Not as detailed as case details. |
| 6 | **ServiceNow HRSD Get User Cases** | List of user cases |
| 7 | **ServiceNow HRSD System Get Cases List** | This topic isn't an editable topic. Get user cases calls this for further processing. |
| 8 | **ServiceNow HRSD System Get Metadata Cached** |         |
| 9 | **ServiceNow HRSD System Common Execution** |         |
| 10 | **ServiceNow HRSD System Case Details Cache Lookup** |         |
| 11 | **ServiceNow HRSD System Graceful Exit**  |         |

### Flows

The following Flows are available from the ServiceNow HRSD extension pack:

| Serial no. | Flow | Description |
|---------|---------|---------|
| 1 | **ServiceNow HRSD Common Create Record** |  |
| 2 | **ServiceNow HRSD Common Get Record** |  |
| 3 | **ServiceNow HRSD Common List Records** |  |
| 4 | **ServiceNow HRSD Common Orchestrator** |  |
| 5 | **ServiceNow HRSD Common Update Record** |  |
| 6 | **ServiceNow HRSD Create Case** |  |
| 7 | **ServiceNow HRSD Get Case Details** |  |
| 8 | **ServiceNow HRSD Get Cases List** |  |
| 9 | **ServiceNow HRSD Get HR Services with COEs for User** | |

## ServiceNow - ITSM

### Topics

The following Topics are available from the ServiceNow ITSM extension pack:

| Topic | Description |
|---------|---------|
| **ServiceNow ITSM Create Ticket** | This topic takes user input like description, severity, etc. and sends these details to the corresponding system topic. Successful creation generates another adaptive card with ticket details. |
| **ServiceNow ITSM Get User Tickets** | This topic fetches the active or closed tickets, and does a quick check on a global variable, which we are using as cache for this data. |
| **ServiceNow ITSM Get Ticket Details** | This topic acquires the *sysID* and passes it down to corresponding system topic. |
| **ServiceNow ITSM Update Ticket** | This topic gets the *sysID* and other necessary input required for the update call. Also validates if the user has necessary permission to update that ticket. |
| **ServiceNow ITSM Get Ticket Updates** | This topic retrieves the latest update of IT support tickets for the user. It fetches the list of tickets and then provides the update related to the latest one. |

### Modify template configurations

For any required modifications to the backend ServiceNow Incident APIs, the template configurations for each scenario can be adjusted in coordination with updates to the frontend topics.

To access the template configurations:

1. Navigate to the overview tab within the ESS Agent and scroll down to the ***Customize*** tab
2. Select the installed customization titled ***Employee Self Service IT Helpdesk ServiceNow ITSM***
3. This action redirects you to the installed customization details page, where you can view all the Topics and Flows included in the customization package. Additionally, there's a ***Configuration*** option at the top with a manage button
4. By selecting the manage button, you're directed to the Dataverse Template Configurations table, which lists all available template configurations.
5. Select the specific scenario template configuration, and it opens the actual value in the Dynamics 365 webpage in a new tab, which can edit the JSON as needed and save your changes

### Capabilities for the ServiceNow extension pack

Based on the SNOW connector and public APIs, the Service NOW extension pack includes several capabilities. **The initial version focuses on Incident Management**. Specifically, it offers Create, Read, and Update (CRU) functionalities for managing ServiceNow incidents.

#### Get Ticket Status

This function allows users to retrieve the latest status of a ticket using ServiceNow APIs, enabling seamless integration with existing IT workflows. By accessing real-time ticket status information, users can efficiently track the progress of reported issues.

#### Get Ticket Details

The Get Ticket Details feature enables users to retrieve comprehensive information about a specific ticket within the ServiceNow platform. This functionality provides user details of attributes such as the ticket number, short description, full description, and current state.
By providing these details, users can gain a complete understanding of the ticket's context
and status, facilitating more effective issue resolution and communication.

#### Get Ticket List

The Get Ticket List feature allows users to retrieve a history of tickets of the user. This functionality provides essential details about each ticket, including its unique number, a brief description, the status, and the date of the last update.

#### Create Ticket

Provides user the ability to create a ticket for IT helpdesk support.

Users can easily add attachments to the ticket enabling them to provide more context for easier resolution. (Post Private Preview)

#### Update Ticket

The Update Ticket feature allows users to modify existing helpdesk tickets by adding comments and attributes. This functionality is crucial for maintaining clear and concise communication between users and support agents, ultimately enhancing the resolution process.

Users can easily add attachments to the ticket enabling them to provide more context for easier resolution. (Post Private Preview)

### ServiceNow ITSM template configurations

These JSON configurations are intended for the ServiceNow APIs within the backend, facilitating the linkage between input and output variables from and to the bot. Each scenario has a corresponding JSON configuration, enabling extension pack users to adjust the parameters utilized in the APIs without altering anything in the backend workflows. The way the backend interacts with bot topics regarding input and output variables is defined within these configurations.
The template configurations reside within a custom Dataverse table, created through the ESS base package upon installation in an environment. Extension packs contribute extra rows to this table, each containing a stringified JSON configuration for a specific scenario. These configurations are retrieved at runtime using the Dataverse connectors within Power Automate flows.

### Understanding configurations naming

- **Scenario**: The name of the scenario used as the identifier of the operation. This is the primary key for the template configuration and shouldn't be changed.
- **FilterCriteria**: This criterion is used to filter the ServiceNow table by applying the "Operator" on a specific "FieldName". "VariableName" refers to the name of the variable passed from the bot topics containing the actual value. If this variable isn't mandatory, the bot author may choose not to send it.
- **SortCriteria**: Used to sort the list of records from a ServiceNow Table on "FieldName" by "Operator".
- **Limit**: Maximum number of records to return.
- **Offset**: Starting record index for which to begin retrieving records.
- **DisplaySystemReferences**: Flag that indicates the type of data returned, either the actual values from the DB or the display values of the fields.
- **ExcludeReferenceLinks**: Flag that indicates whether to exclude Table API links for reference fields.
- **OutputFieldMapping**: Used to model the ServiceNow Table API output to JSON understood by the bot. Corresponding "FieldName" is mapped to "OutputName".
- **UserParameters (InputFieldMapping)**: Values of the fields that need to be passed from the user via the bot to the backend flows. Used in case of creating and updating.
- **GlobalParameters (InputFieldMapping)**: Global values that are consistently passed to the API with each call. These include essential values such as AssignmentGroup, which remain unchanged in every case.

## References

- [ServiceNow - Connectors](/connectors/service-now/#actions)
- [External ID Token Authentication (OIDC) for Rest APIs - Support and Troubleshooting](https://support.servicenow.com/kb?id=kb_article_view&sysparm_article=KB0720547)
- [ServiceNow Catalog Microsoft 365 Copilot connector | Microsoft Learn](/microsoftsearch/servicenow-catalog-connector#3-authentication-type)

For ServiceNow Knowledge documentation, refer to the following, which requires ServiceNow logins:

- [Table API](https://www.servicenow.com/docs/bundle/xanadu-api-reference/page/integrate/inbound-rest/concept/c_TableAPI.html)