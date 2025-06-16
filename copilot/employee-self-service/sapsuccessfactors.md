---
title: Integrate SAP SuccessFactors with your Employee Self-Service deployment
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
description: Learn about integrating SAP SuccessFactors in the deployment process for the Employee Self-Service agent.
appliesto:
  - ✅ Microsoft 365 Copilot
---

# Integrate SAP SuccessFactors with your Employee Self-Service deployment

> [!IMPORTANT]
> This is a Copilot agent built by Microsoft that's still in preview and subject to changes.
>
> Previews may not work correctly or in the manner that a commercial service may function. Unless otherwise noted in a separate agreement, previews are not included in the Service Level Agreement for the corresponding Online Service and may not be covered by customer support. We may change or discontinue previews at any time without notice. We may also choose not to make a preview generally commercially available. We may update previews at any time and for any reason, which may result in the deletion of Participant Data.
>
> Participant’s use of previews in a live production environment is at Participant’s sole discretion and own risk. Participant acknowledges that Previews may contain bugs or other errors that could cause Previews, any system they run on, and any applications running on them to malfunction or experience impaired performance, including the loss of Participant Data.

## Overview

ESS Agent is a new capability built by Microsoft that runs on top of Copilot leveraging Artificial Intelligence (AI) in providing relevant information to employees and taking actions on their HR data.

As most organizations manage HR data in a HRIS/HCM systems, ESS Agent should have access to HR data on behalf of users. SAP SuccessFactors is one of the HCM systems, this document will guide through the process required to integrate ESS Agent with SAP SuccessFactors.

ESS Agent will continue to serve as unified assistants for employees to provide HR related services and connecting with SAP SuccessFactors makes it truly an enterprise HR assistant.

## Functional Synopsis

ESS Agent will act as a front-end for consuming information from SAP SuccessFactors. The following are the scenarios currently supported by ESS Agent for SAP SuccessFactors integration:

- Get Base Compensation
- Get Company Code
- Get Cost Center
- Get Hire Date
- Get Service Anniversary
- Get Employee Id
- Get Job Info
- Get Position Number

## Technical Synopsis

<image 1>

The above diagram outlines the high-level components comprising overall solution for ESS Agent and SuccessFactors integration. There are different activities to be performed as part of initial deployment and for an ongoing operation. As the solution involves multiple technologies, it’s better to spend some time initially in understanding the various components and bring in the right stakeholders to set up an environment to deploy and test ESS Agent.

> [!NOTE]
> SuccessFactors integration is currently based on OData V2.0, but the latest supported version is V4.0 Microsoft Entra ID using SuccessFactors is still a prerelease version and is subject to change.

## Prerequisites

- [Setup SAP OData connector](/power-platform/sap/connect/sap-odata-connector)
- Admin access to SAP SuccessFactors
- Admin access within the Azure Portal

You can refer to the ESS Agent deployment guide for subscription requirements required for the ESS Agent itself.

## Deployment role requirements

| **Roles / Persona**    | **Description** | **Activities performed** | **Configuration Areas**   |
| --------- | ----------------------------- | ---------------------------------------- | ------------------------- |
| **SAP SF Administrator** | User who can perform administrative tasks  |  1. Create an OAuth 2.0 Client Application in SuccessFactors <br> 2. Upload the SAML certificate to OAuth 2.0 Client Application within SuccessFactors <br>3. Determine the API server where SF is hosted <br> 4. Confirm the maker account mapped in SAP SF have OData API access | SAP SuccessFactors |
| **Application Administrator (or) Cloud Application Administrator (or) Application Owner** | User who can configure Single SignOn (SSO) integration   | 1. Establish a Microsoft Enterprise Application <br> 2. Configure SAML settings within the Enterprise Application <br> 3. Obtain the Enterprise Application’s SAML certificate <br> 4. Establish trust | Azure Admin Portal  |
| **Environment Maker** | User who can customize ESS Agent  | 1. Install and configure SAP SF Extension Pack <br> 2. Manage SAP SF Topics <br> 3. Setup User Context  | Microsoft Copilot Studio  |
| **InfoSec/IT Infra/Change Control Board**  | User committee who are responsible for security infrastructure changes | 1. Configure IT platform services such as network and firewall rules| Network firewall policies |

### Infra setup for 3P ISV integration

Most enterprise organizations have secured their 3P HCMs/Knowledge Sources, etc. from external networks, as it’s critical for the line of business to protect sensitive information about employees, organizations, knowledge assets, etc.

When there’s a need to integrate these enterprise systems into ESS Agent to use it as a source for providing relevant information to the end users, these systems should be accessible to the Power Platform environment where these ESS Agents are hosted.

These systems must be configured with allow lists for the source IP addresses from where the ESS Agent is hosted and executed, i.e. Power Platform environment. 

For overall Power Platform URLs and IP address ranges, see [Power Platform URLs and IP address ranges - Power Platform](/power-platform/admin/online-requirements).

For 3P ISV connectors, see [Managed connectors outbound IP addresses](/connectors/common/outbound-ip-addresses#power-platform).

For SAP SuccessFactors (SF) integration, as ESS Agent uses OData v2.0, it’s required to work with InfoSec to allowlist Power Platform connectors to communicate with this endpoint. If any additional data security requirements are to be met esp. for OData exchange, work with your security specialists to harden the security for data in transit.

### Setup SSO for SAP SuccessFactors with Entra

You can ignore this step if SSO is already established for SAP SuccessFactors with Entra.

Below is a high-level overview of the OAuth Authentication process in SAP SuccessFactors:

#### Parameters for SuccessFactors connection

- **SuccessFactors Token API**
- **SuccessFactors Client ID**
- **App Resource URI** (`format: api://<App-ID>`)
- **SuccessFactors OData Base URI**
- **Company ID** - Represents the specific SuccessFactors environment for login

#### Key configuration notes

- **User mapping**: Ensure that the Unique User Identifier claim of the Microsoft Entra ID user aligns precisely with the **user alias** in SuccessFactors (*one-to-one matching*).
- **User access control**: Only users or groups listed in the Enterprise Application will be allowed to authenticate SuccessFactors.
- **Resource URI**: Found in the Enterprise App settings under Expose an API as the Application ID URI.
- **Company ID**: It is based on the enabled SuccessFactors modules.

#### High-level overview

1. Establish a *Microsoft Enterprise Application*.
2. Create an *OAuth 2.0 Client Application* in SuccessFactors.
3. Configure *SAML* settings within the Enterprise Application.
4. Obtain the Enterprise Application's *SAML Certificate*.
5. Upload the SAML Certificate to your OAuth 2.0 Client Application within SuccessFactors.
6. Establish trust.

### Create a Microsoft Entra ID Enterprise Application

1. Open the Azure Portal and go to **Microsoft Entra ID > Enterprise Applications**.
2. Select **New application**.
3. Search for and select **SAP SuccessFactors**
4. Assign a name for the application and select **Create**
5. Go to **Single sign-on** and select **SAML**
6. Follow specific guidelines in the **SuccessFactors SSO Configuration Guide** 
7. Configure the following:
   1. **Identifier (Entity ID)**: Set to `api://<Enterprise App ID>` (e.g., `api://33135bc6be6a-4cdc-9c96-af918e367425`)
     > [!NOTE]
     > Recommended to use the SF instance URL `https://<sfinstance>.successfactors.com`

   2. **Reply URL**: Used in the SAML token as the Recipient field (e.g., `https://<apiserver>/oauth/token`)

     > [!NOTE]
     > This is important for the claims process to which the API server where SF instance is hosted must be provided, for example if the SF instance is hosted in one of the API servers `api68sales.successfactors.com`, then the URL should be `https://api68sales.successfactors/oauth/token`.
     > For more information on the SF documentation to determine the API server, see [List of SAP SuccessFactors API Servers](https://help.sap.com/docs/successfactors-platform/sap-successfactors-api-reference-guide-odata-v2/list-of-sap-successfactors-api-servers).

   3. **Sign-On URL**: Advisable to set as `https://<your-sfurl>/sf/start?company=<CompanyID>&logonMethod=SSO`.
     > [!NOTE]
     > If SF instance for Contoso Corporation is "Contoso" and company ID is "CNTPART000100", then the URL will look as below: `<https://contoso.successfactors.com/sf/start?company=CNTPART000100&loginMethod=SSO`.

8. Edit the Attributes and Claims section: (come to this section after completing the creation of OAUTH 2.0 Client application in SuccessFactors)
    1. Add a claim for api_key with the value of the API Key from SuccessFactors
    2. Update the *Unique User Identifier* claim to match the unique ID for each SuccessFactors user

     > [!NOTE]
     > Choose the correct name identifier format based on the user mapping between Entra and SAP SuccessFactors. For example, if "Employee ID" is used as a login user ID for SAP SuccessFactors, then the mapping of source attribute should be the correct attribute from Entra and since this is just an Employee ID without any email format, the **Name identifier format** should be set as **Unspecified**.

9. Download the **Certificate (Base64 format)** from this application – this is required for completing the next step of creating an OAuth 2.0 Client Application in SuccessFactors. A certificate can be downloaded without completing the step #8 above and complete the OAuth 2.0 Client application setup in SuccessFactors to obtain the "api_key", which is required to complete the previous step.
10. Assign users and groups – add all the users and/or groups required to access SAP SF via the ESS Agent under “Users and groups" section within Enterprise applications configuration for SAP SuccessFactors application created in Entra.

### Create an OAuth 2.0 Client Application in SuccessFactors

1. Log in to the *SuccessFactors Web UI* with an admin account.
2. Go to Manage OAuth2 Client Applications.
3. Select Register Client Application.
4. Fill out the required fields:
    1. **Company:** Auto-populated
    2. **Application Name:** Any descriptive name
    3. **Description:** Any descriptive text
    4. **Application URL:** Can be any random URL
    5. **X.509 Certificate:** Copy/paste the certificate downloaded from step #9 in the "Create a Microsoft Entra ID application" section. 
     > [!NOTE]
     > The certificate file need to be renamed as a text file to open in a text editor, then copy/paste the crypted characters without including the header & footer lines.

5. Select **Save**. The new client application now has an **API Key** that serves as *Client ID* in SAML2 session flow and is used in the connection and Enterprise App configuration.

### Configure Enterprise Application

1. In the **Azure Portal**, go to **App Registrations,** select **SAP SuccessFactors** application created in the previous section.
2. Under **Expose an API**, locate **Resource URI** (Application ID URI).
3. Select **Add a client application**.
4. Enter the Client ID for SAP OData: `6bee4d13-fd19-43de-b82c-4b6401d174c3`.
5. Select the existing scope from the **Authorized scopes** checklist
6. Select **Add application**.
7. Navigate to Enterprise instance and add the users who need access to SF OData API.

### Configure SuccessFactors to trust Microsoft Entra ID

1. Log in to the SuccessFactors Web UI with an admin account.
2. Go to **Manage OAuth2 Client Applications**.
3. Select the client application that’s been created earlier.
4. Update the certificate to the one downloaded from Microsoft Entra ID and paste only the certificate body content without the header and footer.

#### Test the connection

1. Open **Power Automate** in your browser.
2. Create a new flow (manual trigger type).
3. Add an **SAP OData** action.
4. Select **Microsoft Entra ID using SuccessFactors** as the connection.
5. Fill in the required parameters gathered earlier.
6. Choose an **Entity** from the dropdown to test.
7. Save your flow.
8. Run the flow to test the connection.
9. Verify the run history for successful authentication and data retrieval.

For more information on setting up SSO for SAP SuccessFactors with Entra, see [Set up Microsoft Entra ID using SuccessFactors](power-platform/sap/connect/entra-id-using-successfactors).

## Install SuccessFactors Extension Pack for ESS Agent

ESS Agent is designed to have separate extension packs for each third party ISVs like SuccessFactors, etc. Hence, these extension packs must be installed first before starting any configurations or customizations.

The following are the steps required to install & enable the SuccessFactors Extension Pack:

1. Work with your ESS Agent private preview product managers for the entitlement process. Once the entitlement process is complete for your tenant, the SuccessFactors extension pack will show up under **Customize** section of ESS Agent.

   > [!NOTE]
   > Entitlement process is a preview workaround until the extension pack installation is streamlined in Microsoft Copilot Studio.

2. Install the extension.
   1. Open the ESS Agent in Copilot Studio.
   2. Navigate to **Settings**.
   3. Select **Customize** from the left navigation under the Settings.
   4. Select **Employee Self Service HR SuccessFactors** and click **Install**.
   5. When prompted, update the connections as described by clicking **...** buttons on the righthand side for each connection.
   6. The first connection is the user account which should be automatically signed in
   7. The second connection is for the OData API which requires the following parameters to be configured.

**Parameters to configure:**

| **Authentication Type**  | **Microsoft Entra ID using SuccessFactors (Preview)** |
| ------------------------------ | ------------------------------------------------------------------------------------- |
| **SuccessFactors token URL**   | SuccessFactors OAuth token endpoint URL  (format: `https://<api-server>/oauth/token`) |
| **Service Provider Client Id** | SuccessFactors OAuth2 Client ID – the api_key |
 **OData Base URI**| Base URI for the OData service `https://<api server>/odata/v2` |
| **Microsoft Entra Resource URI** or **(Application ID URI)** | Identifier used in Microsoft Entra ID to identify the target resource. <br> Application ID URI configured under the section *Create Enterprise Application* |
|**Company ID** |Company ID|

> [!NOTE]
> SAP SF OData Connector uses maker connection in all flows which should use SF API user credentials to establish connection.

## Setup SuccessFactors Extension Pack for ESS Agent

The SuccessFactors extension pack requires few initial setups for the agent flows and templates. The following sections are required to configure the required components:

### Setup User Context

This step is required to set the user context for the ESS Agent, which primarily does the user mapping for Entra and pass it on to SAP SuccessFactors.

1. Open the ESS Agent in Copilot Studio
2. Go to **Topics**
3. Select **\[Admin\] – User Context – Setup**
4. In the canvas, click on **… More** and select **</> Open code editor**
5. Replace the existing code with the following code snippet:

   ```YAML
   kind: AdaptiveDialog 
   beginDialog: 
   kind: OnRedirect 
   id: main 
   priority: 0 
   actions: - kind: SetVariable 
   id: setVariable_9CWZSL 
   variable: Global.ESS_UserContext_UPN 
   value: =First(Split(System.User.PrincipalName,"@")).Value - kind: BeginDialog 
   id: mRTRN3 
   dialog: 
   msdyn_copilotforemployeeselfservice.topic.SuccessFactorsSystemContextInitializer 
   ```

   > [!NOTE]
   > The highlighted section in the code transforms username from the logged in users’ principal name to SAP SuccessFactors user ID, so please use this based on your environment setup between Entra and SAP SuccessFactors. Currently the agent supports only User Principal Name (UPN) as a key identifier, if there are other attributes to be used as a key identifier then a custom logic should be implemented to get the correct username for SAP SuccessFactors.
6. Click **Save** for changes.

#### Setup Templates

ESS Agent comes with few pre-defined templates that are being used for each Topics. These templates are shipped with the default data attribute paths, if there are custom entities and paths being used in SAP SuccessFactors, then these templates must be customized matching the SAP SuccessFactors entities.

Please follow the steps below to set up templates:

1. Open ESS Agent in Copilot Studio.
2. Click **Settings** in the top right corner of agent ribbon.
3. Select **Customize** from the agent settings left navigation pane.
4. Select **Employee Self Service HR SuccessFactors** extension pack.
5. Click **Open** from the dialog popup.
6. Select **Manage** in the Configuration section.
7. All the template configurations available will be listed in Power Apps, please select each of the "Get" templates to configure the right entities and paths.
8. Following is an example of the Get configuration template

   ```json
   { 
   "scenario": 
   "HRSAPSuccessFactorsHCMEmployeeGetBaseCompensationAndCompaRatio",//Scenario name 
   [OPTIONAL] 
   "rootEntity": "EmpEmployment",//Entity to be queried 
   "filter": "personIdExternal eq '{personIdExternalVal}' and userId eq 
   '{userIdVal}'",//Filter Expression to filter data more on format below 
   SAP integration for ESS Agent 
   NDA Private Preview Customers ONLY 
   Microsoft Corporation © 
   Deployment Guide v0.1 
   Page 13 of 44 
   SAP integration for ESS Agent Deployment Guide v0.1 Page 14 of 44 
   NDA Private Preview Customers ONLY 
   Microsoft Corporation © 
       "requestEntities": [  //Request entites an array of object that should be queried 
   from root entity 
           { 
               "key": "CompaRatio",//Key Value 
               "valuePath": "compInfoNav/empCompensationCalculatedNav/compaRatio",//Path 
   from root entity for value 
               "labelPath": "EmpCompensationCalculated/compaRatio"//Path from label 
   $metadata to get label value 
           }, 
       ], 
       "permissionsMetadata": [  //Permission Metadata more on this in permisson loop 
           { 
               "permType": "DATA_MODEL",  //Permision Type SF code value 
               "permLongValue": -1,   
               "permStringValue": "$_payCompGroup_AnnualizedSalary_read"  //Permission 
   string SF code value 
           } 
       ]
    }
   ```

The highlighted **filter** parameter keys must match what is expected in the Template configuration. In the example below *personIdExternalVal* would be used as a key to insert *Global.ESS.UserContext.Employee_Id* into the filter expression.

**Example format used in topic:**

_`"{""personIdExternalVal"": """ & Global.ESS_UserContext_Employee_Id & """,""userIdVal"": """ & Global.ESS_UserContext_User_Id & """}"`

**Snippet of Template configuration:**

```json
{
"filter": "personIdExternal eq '{personIdExternalVal}' and userId eq '{userIdVal}'", }
```

## Permissions and Role based permissions configuration

There are two permissions configs which can be used. The permissions flow will check if **RoleBased** permissions are provided in the config and choose that over permissions metadata otherwise it will always use permissions metadata.

### Permissions Config

The Permissions flow calls the OData Connector with _CheckUserPermission_ as its relative path and _permissionMetadata_ in the config as the queryString. OData connector then returns a true or false value dictating if the user has permission or not and that is returned to the Get Flow.

```json
{ 
.. 
  "permissionsMetadata": [ 
    { 
      "permType": "DATA_MODEL",  //Permision Type SF code value 
"permLongValue": -1,   
"permStringValue": "$_payCompGroup_AnnualizedSalary_read"  //Permission string SF code 
value 
} 
] 
.. 
}
```

### Role Based Permissions Config

Role based permissions uses the _roleId_ provided in the config to check against _UserRoles_ variable that is part of the user context. The flow queries _RBPRole_ with _roleId_ given in config which returns all the _permissionStringValues_ linked to the _roleId_. Then it matches the _permStringValue_ in the config to what the OData connector returned. Manager Scenarios are required to use RBP role because we are checking if the manager has permissions for multiple users at the same time and therefore using _PermissionsMetadata_ would have been slower. In this case, we can check that the user has 115 role which gives him permission to make changes their directs. Role Id must be created by the maker if current SF implementation does not have it.

```json
{ 
.. 
"rolePermissions": [ 
{ 
"roleId": "115", //Role ID code from SF to query for 
"permissions": [ 
{ "permStringValue": "$_employmentInfo_originalStartDate_read" } //Permission string to 
check for in role id 
] 
} 
] 
.. 
} 
```

### User Context Flow – High-level logic

1. Setting a variable with the filter parameters which in this case is the alias of the user the context is retrieved for
2. Next split into parallel calls to reduce time:
    1. Left side retrieves the user context config in the first Dataverse call and 2nd Dataverse call retrieves the filter and request entities which we are going to query for in the OData connector at the end. After Left side is complete the flow will have retrieved all the requested entities from the config for the user.
    2. Right side retrieves Config to check if user _isManager_ in the first Dataverse call and in the 2nd Dataverse call flow retrieves the filter and request entities to query for. With that config the flow queries for directs under the user and retrieves necessary information such as in this case _userId_ of Directs.
3. If SF call for user data doesn't return anything we terminate the flow and respond to copilot user not found
4. Split into parallel calls to check if the user has multiple records on the left
5. The left side checks if there are multiple records and then runs a child flow that gets the active user Id and updates the context. Then the flow makes an OData call to get the user's roles by their user id
6. The right-side checks for open positions if the user is a manager and

**IsManagerCheckVacantPositions** is set to True. It makes Dataverse calls to get the necessary configs to make the SF OData Request then updates _IsManager_ variable

1. Lastly Flow composes an object with all the required user context fields and returns it to CoPilot Studio (CPS) Read Flow – High-level logic

**Input Variables:**

- **loggedInUserId:** alias
- **scenarioName:** Config Name Ex:

"msdyn_HRSAPSuccessFactorsHCMEmployeeGetNationalId"

- **userLocale:** en_US
- **targetUserId:** alias
- **filter:** {"personIdExternalVal": "123456"}
- **userRoles:** \["123", "345"\]

1. The flow retrieves the config using the _scenarioName_ variable and in parallel preps the filter query
2. The flow retrieves the data and label entities from the config using Dataverse plugin
3. Flow calls child flow to check permissions by passing the _userRoles_, alias, and config
4. If Permission flow returns _false_ then the flow will terminate and respond to copilot that user does not have permissions
5. Flow then in parallel makes OData calls for the entity data and the labels.
6. To get the labels first the flow checks if there are any labels to query in the config and then preps the variables which will be needed
7. Flow will Query SF OData Metadata entity using the values collected earlier from the config. Due to the response being metadata the flow does some manipulation to get the data into key value pairs.
8. Lastly it returns 3 variables _labelResponse_, _modelResponse_, and _isSucceeded_

Employee Read Scenarios – Configuration

The Topics that are shipped with ESS Agent preview are limited only for “Read” scenarios and the “Update” scenarios are not supported yet, even thought they are available for the current version (please refer the version history on top of this document) of agent.

Each of the Read scenario Topic have its own prompts, configurations, etc., but the actual execution of SAP SuccessFactors are encapsulated in the **SuccessFactors System Get Common Execution** Topic expecting the following inputs:

- - Filter parameters: Generally passing _Employee ID_ and _User ID_ for filtering query for Employee Read Topics
    - ScenarioName: Config Name which is used by Dataverse call to get scenario configuration
    - userIdentifier: User ID

Common orchestrator then returns a ModelResponse and LabelResponse which is then parsed by the LLM following the below instructions and generates answer for user:

Extract the input from the below response (map the Label response \*value\* as key in model response attribute then provide model value)

Provide response to the user in a human readable form

Format it properly so it looks clean and readable

Use \*\*only\*\* data values from variable named as "successfactorsModelResponse" and use variable named as "successfactorsLabelResponse" for labeling the data

Response Example:

Label Response: key":"company","value":"company"

Model Response: "company":"12345"

Example Output:

Your company is 12345 (Contoso Germany)

The *Get Employee Id* and *Get Service Anniversary* Topics are exception to this common execution method, which are further explained in their respective sections.

Authorization for all the Topics are as follows:

- Authorization is done using the _permissionsMetadata_ that is part of the Template configuration. The _permissionsMetadata_ and _User Id_ are used to create the query string for OData Connector in SuccessFactors Check User Permissions flow
- It is important to include _permissionMetadata_ or _rolePermission_ in template config file as there is no other authorization check if both of those fields are missing

Get Base Compensation

APPENDIX

Troubleshooting:

SAP SF Single Sign-on issues with Entra Pre-requisites for troubleshooting:

- Client tool for testing and managing APIs like Postman, Bruno, etc.
- Access to <https://samltool.io>
- Basic knowledge in how the authentication flow works especially with SAML

Please use the API client tool for testing, validating and confirming the assertion being generated and passed to SF. Refer the SAP support article for more instructions [3462403 - SuccessFactors OData API: OAuth 2.0 Authentication](https://userapps.support.sap.com/sap/support/knowledge/en/3462403)

The following highlighted are the critical pieces of information to be validated as part of claims authentication:

1. _<NameID Format="urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified">_ - please ensure that the correct NameID format is used for user mapping between Entra and SAP SF
2. _<Attribute Name="api_key">_ - please ensure that the claims token have the correct api_key from SAP SF OAuth 2.0 client application created References:

[SAP SuccessFactors API Reference Guide](https://help.sap.com/doc/2d1d6fcc4eae4db8b9bbd3103baee1c7/2411/en-US/HXMSuiteODataAPIRefGuideV4.pdf)

[SAP OData Connector Reference](https://learn.microsoft.com/en-us/connectors/sapodata/)

[Set up Microsoft Entra ID using SuccessFactors (Preview)](https://learn.microsoft.com/en-us/power-platform/sap/connect/entra-id-using-successfactors)

[Get started with the SAP OData connector](https://learn.microsoft.com/en-us/power-platform/sap/connect/sap-odata-connector)
