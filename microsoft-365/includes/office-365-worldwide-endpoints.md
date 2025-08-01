<!--THIS FILE IS AUTOMATICALLY GENERATED. MANUAL CHANGES WILL BE OVERWRITTEN.-->
<!--Please contact the Office 365 Endpoints team with any questions.-->
<!--Worldwide endpoints version 2025073100-->
<!--File generated 2025-07-31 06:12:03.8278-->

## Exchange Online

ID | Category | ER | Addresses | Ports
-- | ---------------------------------------------------------------- | --- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------
1 | Optimize<BR>Required | Yes | `outlook.cloud.microsoft, outlook.office.com, outlook.office365.com`<BR>`13.107.6.152/31, 13.107.18.10/31, 13.107.128.0/22, 23.103.160.0/20, 40.96.0.0/13, 40.104.0.0/15, 52.96.0.0/14, 131.253.33.215/32, 132.245.0.0/16, 150.171.32.0/22, 204.79.197.215/32, 2603:1006::/40, 2603:1016::/36, 2603:1026::/36, 2603:1036::/36, 2603:1046::/36, 2603:1056::/36, 2620:1ec:4::152/128, 2620:1ec:4::153/128, 2620:1ec:c::10/128, 2620:1ec:c::11/128, 2620:1ec:d::10/128, 2620:1ec:d::11/128, 2620:1ec:8f0::/46, 2620:1ec:900::/46, 2620:1ec:a92::152/128, 2620:1ec:a92::153/128` | **TCP:** 443, 80<BR>**UDP:** 443
2 | Allow<BR>Optional<BR>**Notes:** POP3, IMAP4, SMTP Client traffic | Yes | `outlook.office365.com, smtp.office365.com`<BR>`13.107.6.152/31, 13.107.18.10/31, 13.107.128.0/22, 23.103.160.0/20, 40.96.0.0/13, 40.104.0.0/15, 52.96.0.0/14, 131.253.33.215/32, 132.245.0.0/16, 150.171.32.0/22, 204.79.197.215/32, 2603:1006::/40, 2603:1016::/36, 2603:1026::/36, 2603:1036::/36, 2603:1046::/36, 2603:1056::/36, 2620:1ec:4::152/128, 2620:1ec:4::153/128, 2620:1ec:c::10/128, 2620:1ec:c::11/128, 2620:1ec:d::10/128, 2620:1ec:d::11/128, 2620:1ec:8f0::/46, 2620:1ec:900::/46, 2620:1ec:a92::152/128, 2620:1ec:a92::153/128` | **TCP:**  587,  993,  995, 143
8 | Default<BR>Required | No | `*.outlook.com, autodiscover.<tenant>.onmicrosoft.com` | **TCP:** 443, 80
9 | Allow<BR>Required | Yes | `*.protection.outlook.com`<BR>`40.92.0.0/15, 40.107.0.0/16, 52.100.0.0/14, 52.238.78.88/32, 104.47.0.0/17, 2a01:111:f400::/48, 2a01:111:f403::/48` | **TCP:** 443
10 | Allow<BR>Required | Yes | `*.mail.protection.outlook.com, *.mx.microsoft`<BR>`40.92.0.0/15, 40.107.0.0/16, 52.100.0.0/14, 104.47.0.0/17, 2a01:111:f400::/48, 2a01:111:f403::/48` | **TCP:** 25

## SharePoint Online and OneDrive for Business

ID | Category | ER | Addresses | Ports
-- | -------------------------------------------------------------------------------------------------------------------------------------- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------
31 | Optimize<BR>Required | Yes | `*.sharepoint.com`<BR>`13.107.136.0/22, 40.108.128.0/17, 52.104.0.0/14, 104.146.128.0/17, 150.171.40.0/22, 2603:1061:1300::/40, 2603:1063:6000::/35, 2620:1ec:8f8::/46, 2620:1ec:908::/46, 2a01:111:f402::/48` | **TCP:** 443, 80<BR>**UDP:** 443
32 | Default<BR>Optional<BR>**Notes:** OneDrive for Business: supportability, telemetry, APIs, and embedded email links | No | `storage.live.com` | **TCP:** 443
33 | Default<BR>Optional<BR>**Notes:** SharePoint Hybrid Search - Endpoint to SearchContentService where the hybrid crawler feeds documents | No | `*.search.production.apac.trafficmanager.net, *.search.production.emea.trafficmanager.net, *.search.production.us.trafficmanager.net` | **TCP:** 443
35 | Default<BR>Required | No | `*.wns.windows.com, admin.onedrive.com, officeclient.microsoft.com` | **TCP:** 443, 80
36 | Default<BR>Required | No | `g.live.com, oneclient.sfx.ms` | **TCP:** 443, 80
37 | Default<BR>Required | No | `*.sharepointonline.com, spoprod-a.akamaihd.net` | **TCP:** 443, 80
39 | Default<BR>Required | No | `*.svc.ms` | **TCP:** 443, 80

## Microsoft Teams

ID | Category | ER | Addresses | Ports
--- | -------------------------------------------------------------------------------- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------
11 | Optimize<BR>Required | Yes | `52.112.0.0/14, 52.122.0.0/15, 2603:1063::/38` | **UDP:** 3478, 3479, 3480, 3481
12 | Allow<BR>Required | Yes | `*.lync.com, *.teams.cloud.microsoft, *.teams.microsoft.com, teams.cloud.microsoft, teams.microsoft.com`<BR>`52.112.0.0/14, 52.122.0.0/15, 2603:1027::/48, 2603:1037::/48, 2603:1047::/48, 2603:1057::/48, 2603:1063::/38, 2620:1ec:6::/48, 2620:1ec:40::/42` | **TCP:** 443, 80<BR>**UDP:** 443
16 | Default<BR>Required | No | `*.keydelivery.mediaservices.windows.net, *.streaming.mediaservices.windows.net` | **TCP:** 443
17 | Default<BR>Required | No | `aka.ms` | **TCP:** 443
19 | Default<BR>Optional<BR>**Notes:** For end user and customer owned device updates | No | `adl.windows.com` | **TCP:** 443, 80
27 | Default<BR>Required | No | `join.secure.skypeassets.com, mlccdnprod.azureedge.net` | **TCP:** 443
127 | Default<BR>Required | No | `*.skype.com` | **TCP:** 443, 80

## Microsoft 365 Common and Office Online

ID | Category | ER | Addresses | Ports
--- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------
46 | Allow<BR>Required | Yes | `*.officeapps.live.com, *.online.office.com, office.live.com`<BR>`13.107.6.171/32, 13.107.18.15/32, 13.107.140.6/32, 52.108.0.0/14, 52.244.37.168/32, 2603:1006:1400::/40, 2603:1016:2400::/40, 2603:1026:2400::/40, 2603:1036:2400::/40, 2603:1046:1400::/40, 2603:1056:1400::/40, 2603:1063:2000::/38, 2620:1ec:c::15/128, 2620:1ec:8fc::6/128, 2620:1ec:a92::171/128, 2a01:111:f100:2000::a83e:3019/128, 2a01:111:f100:2002::8975:2d79/128, 2a01:111:f100:2002::8975:2da8/128, 2a01:111:f100:7000::6fdd:6cd5/128, 2a01:111:f100:a004::bfeb:88cf/128` | **TCP:** 443, 80
47 | Default<BR>Required | No | `*.office.net` | **TCP:** 443, 80<BR>**UDP:** 443
49 | Default<BR>Required | No | `*.onenote.com` | **TCP:** 443
50 | Default<BR>Optional<BR>**Notes:** OneNote notebooks (wildcards) | No | `*.microsoft.com` | **TCP:** 443
51 | Default<BR>Required | No | `*cdn.onenote.net` | **TCP:** 443
53 | Default<BR>Required | No | `ajax.aspnetcdn.com, apis.live.net, officeapps.live.com, www.onedrive.com` | **TCP:** 443
56 | Allow<BR>Required | Yes | `*.auth.microsoft.com, *.msftidentity.com, *.msidentity.com, account.activedirectory.windowsazure.com, accounts.accesscontrol.windows.net, adminwebservice.microsoftonline.com, api.passwordreset.microsoftonline.com, autologon.microsoftazuread-sso.com, becws.microsoftonline.com, ccs.login.microsoftonline.com, clientconfig.microsoftonline-p.net, companymanager.microsoftonline.com, device.login.microsoftonline.com, graph.microsoft.com, graph.windows.net, login-us.microsoftonline.com, login.microsoft.com, login.microsoftonline-p.com, login.microsoftonline.com, login.windows.net, logincert.microsoftonline.com, loginex.microsoftonline.com, nexus.microsoftonline-p.com, passwordreset.microsoftonline.com, provisioningapi.microsoftonline.com`<BR>`20.20.32.0/19, 20.190.128.0/18, 20.231.128.0/19, 40.126.0.0/18, 2603:1006:2000::/48, 2603:1007:200::/48, 2603:1016:1400::/48, 2603:1017::/48, 2603:1026:3000::/48, 2603:1027:1::/48, 2603:1036:3000::/48, 2603:1037:1::/48, 2603:1046:2000::/48, 2603:1047:1::/48, 2603:1056:2000::/48, 2603:1057:2::/48` | **TCP:** 443, 80
59 | Default<BR>Required | No | `*.hip.live.com, *.microsoftonline-p.com, *.microsoftonline.com, *.msauth.net, *.msauthimages.net, *.msecnd.net, *.msftauth.net, *.msftauthimages.net, *.phonefactor.net, enterpriseregistration.windows.net` | **TCP:** 443, 80
64 | Allow<BR>Required | Yes | `*.protection.office.com, *.security.microsoft.com, compliance.microsoft.com, defender.microsoft.com, protection.office.com, purview.microsoft.com, security.microsoft.com`<BR>`13.107.6.192/32, 13.107.9.192/32, 2620:1ec:4::192/128, 2620:1ec:a92::192/128` | **TCP:** 443
66 | Default<BR>Required | No | `*.portal.cloudappsecurity.com` | **TCP:** 443
69 | Default<BR>Required | No | `*.aria.microsoft.com, *.events.data.microsoft.com` | **TCP:** 443
70 | Default<BR>Required | No | `*.o365weve.com, amp.azure.net, appsforoffice.microsoft.com, assets.onestore.ms, auth.gfx.ms, c1.microsoft.com, dgps.support.microsoft.com, docs.microsoft.com, msdn.microsoft.com, platform.linkedin.com, prod.msocdn.com, shellprod.msocdn.com, support.microsoft.com, technet.microsoft.com` | **TCP:** 443
71 | Default<BR>Required | No | `*.office365.com` | **TCP:** 443, 80
73 | Default<BR>Required | No | `*.aadrm.com, *.azurerms.com, *.informationprotection.azure.com, ecn.dev.virtualearth.net, informationprotection.hosting.portal.azure.net` | **TCP:** 443
75 | Default<BR>Optional<BR>**Notes:** Graph.windows.net, Office 365 Management Pack for Operations Manager, SecureScore, Azure AD Device Registration, Forms, StaffHub, Application Insights, captcha services | No | `*.sharepointonline.com, dc.services.visualstudio.com, mem.gfx.ms` | **TCP:** 443
78 | Default<BR>Optional<BR>**Notes:** Some Office 365 features require endpoints within these domains (including CDNs). Many specific FQDNs within these wildcards have been published recently as we work to either remove or better explain our guidance relating to these wildcards. | No | `*.microsoft.com, *.msocdn.com, *.onmicrosoft.com` | **TCP:** 443, 80
79 | Default<BR>Required | No | `o15.officeredir.microsoft.com, officepreviewredir.microsoft.com, officeredir.microsoft.com, r.office.microsoft.com` | **TCP:** 443, 80
83 | Default<BR>Required | No | `activation.sls.microsoft.com` | **TCP:** 443
84 | Default<BR>Required | No | `crl.microsoft.com` | **TCP:** 443, 80
86 | Default<BR>Required | No | `office15client.microsoft.com, officeclient.microsoft.com` | **TCP:** 443
89 | Default<BR>Required | No | `go.microsoft.com` | **TCP:** 443, 80
91 | Default<BR>Required | No | `ajax.aspnetcdn.com, cdn.odc.officeapps.live.com` | **TCP:** 443, 80
92 | Default<BR>Required | No | `officecdn.microsoft.com, officecdn.microsoft.com.edgesuite.net, otelrules.azureedge.net` | **TCP:** 443, 80
93 | Default<BR>Optional<BR>**Notes:** ProPlus: auxiliary URLs | No | `*.virtualearth.net, c.bing.net, ocos-office365-s2s.msedge.net, tse1.mm.bing.net, www.bing.com` | **TCP:** 443, 80
95 | Default<BR>Optional<BR>**Notes:** Outlook for Android and iOS | No | `*.acompli.net, *.outlookmobile.com` | **TCP:** 443
96 | Default<BR>Optional<BR>**Notes:** Outlook for Android and iOS: Authentication | No | `login.windows-ppe.net` | **TCP:** 443
97 | Default<BR>Optional<BR>**Notes:** Outlook for Android and iOS: Consumer Outlook.com and OneDrive integration | No | `account.live.com, login.live.com` | **TCP:** 443
105 | Default<BR>Optional<BR>**Notes:** Outlook for Android and iOS: Outlook Privacy | No | `www.acompli.com` | **TCP:** 443
114 | Default<BR>Optional<BR>**Notes:** Office Mobile URLs | No | `*.appex-rf.msn.com, *.appex.bing.com, c.bing.com, c.live.com, partnerservices.getmicrosoftkey.com, signup.live.com` | **TCP:** 443, 80
116 | Default<BR>Optional<BR>**Notes:** Office for iPad URLs | No | `account.live.com, auth.gfx.ms, login.live.com` | **TCP:** 443, 80
117 | Default<BR>Optional<BR>**Notes:** Viva Engage | No | `<tenant>.yammer.com, <tenant>.yammerusercontent.com` | **TCP:** 443
118 | Default<BR>Optional<BR>**Notes:** Viva Engage Assets CDN | No | `*.assets-yammer.com` | **TCP:** 443
121 | Default<BR>Optional<BR>**Notes:** Planner: auxiliary URLs | No | `www.outlook.com` | **TCP:** 443, 80
122 | Default<BR>Optional<BR>**Notes:** Sway CDNs | No | `eus-www.sway-cdn.com, eus-www.sway-extensions.com, wus-www.sway-cdn.com, wus-www.sway-extensions.com` | **TCP:** 443
124 | Default<BR>Optional<BR>**Notes:** Sway | No | `sway.com, www.sway.com` | **TCP:** 443
125 | Default<BR>Required | No | `*.entrust.net, *.geotrust.com, *.omniroot.com, *.public-trust.com, *.symcb.com, *.symcd.com, *.verisign.com, *.verisign.net, cacerts.digicert.com, cert.int-x3.letsencrypt.org, crl.globalsign.com, crl.globalsign.net, crl.identrust.com, crl3.digicert.com, crl4.digicert.com, isrg.trustid.ocsp.identrust.com, mscrl.microsoft.com, ocsp.digicert.com, ocsp.globalsign.com, ocsp.msocsp.com, ocsp2.globalsign.com, ocspx.digicert.com, oneocsp.microsoft.com, secure.globalsign.com, www.digicert.com, www.microsoft.com` | **TCP:** 443, 80
126 | Default<BR>Optional<BR>**Notes:** Connection to the speech service is required for Office Dictation features. If connectivity is not allowed, Dictation will be disabled. | No | `officespeech.platform.bing.com` | **TCP:** 443
147 | Default<BR>Required | No | `*.office.com, www.microsoft365.com` | **TCP:** 443, 80
152 | Default<BR>Optional<BR>**Notes:** These endpoints enable the Office Scripts functionality in Office clients available through the Automate tab and the Python in Excel functionality available through the Formulas tab. The Office Scripts feature can also be disabled through the Office 365 Admin portal. For admin controls related to Python in Excel, see [Data security and Python in Excel](https://support.microsoft.com/office/data-security-and-python-in-excel-33cc88a4-4a87-485e-9ff9-f35958278327). | No | `*.microsoftusercontent.com` | **TCP:** 443
153 | Default<BR>Required | No | `*.azure-apim.net, *.flow.microsoft.com, *.powerapps.com, *.powerautomate.com` | **TCP:** 443
156 | Default<BR>Required | No | `*.activity.windows.com, activity.windows.com` | **TCP:** 443
158 | Default<BR>Required | No | `*.cortana.ai` | **TCP:** 443
159 | Default<BR>Required | No | `admin.microsoft.com` | **TCP:** 443, 80
160 | Default<BR>Required | No | `cdn.odc.officeapps.live.com, cdn.uci.officeapps.live.com` | **TCP:** 443, 80
184 | Default<BR>Required | No | `*.cloud.microsoft, *.static.microsoft, *.usercontent.microsoft` | **TCP:** 443<BR>**UDP:** 443
