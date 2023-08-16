<!-- loio0c3b5dc775794703b57ed7b01f679e45 -->

# SAP BTP Integration Scenario

Integrating SAP BTP with SAP Cloud Identity Services - Identity Authentication and Identity Provisioning enables user authentication to SAP BTP as well as applications running on SAP BTP and user synchronization between SAP BTP and Identity Authentication.



<a name="loio0c3b5dc775794703b57ed7b01f679e45__section_lgt_sjs_wxb"/>

## Overview

SAP Business Technology Platform \(SAP BTP\) enables you to build and extend SAP applications or subscribe to and consume our integrated offerings. Integrating SAP BTP with SAP Cloud Identity Services is the first to integrating our solutions.

Users fall into two categories:

-   Platform users are usually developers, administrators or operators who deploy, administer, and troubleshoot applications and services on SAP BTP. They’re the users that you give certain permissions for instance at global account or subaccount level or as developers or operators in particular development environments.

-   Business users use the applications that are deployed to SAP BTP. For example, the end users of SaaS apps or services, such as SAP Workflow service or SAP Cloud Integration, or end users of your custom applications are business users.


Your organization can decide to host these different categories of users in the same or different identity providers. Hosting them in SAP Cloud Identity Services - Identity Authentication gives you a number of advantages over SAP ID service which is the default identity provider of SAP BTP. More precisely, you can control your own user lifecycle and single sign-on strategies, as well as define your own password and authentication policies.

In this integration scenario, Identity Authentication acts as your identity provider and SAP BTP acts as your service provider. Identity Provisioning in between provides the connectors to replicate your users from the identity provider to the local user storage of SAP BTP. In SAP BTP, you map the local users to their authorizations in SAP BTP, whether for platform access or to consume business applications.

To accommodate different levels and environments of SAP BTP, Identity Provisioning offers different connectors. The following table describes when to use which connector for which level.

**SAP BTP and Connectors of Identity Provisioning**


<table>
<tr>
<th valign="top" colspan="2">

Account Level



</th>
<th valign="top">

Provisioning



</th>
</tr>
<tr>
<td valign="top" colspan="2">

Global Accounts and Directories \(Feature Set B\)



</td>
<td valign="top">

Use SAP BTP cockpit or the btp CLI to create these platform users in feature set B.



</td>
</tr>
<tr>
<td valign="top" rowspan="4">

Multi-Environment Subaccounts



</td>
<td valign="top">

 



</td>
<td valign="top">

Use *SAP BTP XS Advanced UAA* connector to provision platform and business users at this level from your identity provider.



</td>
</tr>
<tr>
<td valign="top">

Cloud Foundry



</td>
<td valign="top">

Use SAP BTP cockpit.



</td>
</tr>
<tr>
<td valign="top">

ABAP



</td>
<td valign="top">

Use *SAP BTP ABAP Environment* connector to provision users to your virtual ABAP system from your identity provider.



</td>
</tr>
<tr>
<td valign="top">

Kyma



</td>
<td valign="top">

Separate identity provider trust. Manage users in your Identity Authentication tenant.



</td>
</tr>
<tr>
<td valign="top" colspan="2">

Neo Subaccounts



</td>
<td valign="top">

-   Platform users: Use *SAP BTP Account Members \(Neo\)* connector.

-   Business users: Use *SAP BTP Java/HTML5 apps \(Neo\)* connector.




</td>
</tr>
</table>

We assume that you have an Identity Authentication tenant and your users and groups are created there using the methods described in [Identity Lifecycle with an Identity Management Solution](../30-scenario-recommendations/identity-lifecycle-with-an-identity-management-solution-c879f72.md).



<a name="loio0c3b5dc775794703b57ed7b01f679e45__section_fww_bg4_fvb"/>

## Multi-Environment Subaccounts

1.  Establish the trust between your SAP BTP multi-environment subaccount and your Identity Authentication tenant using OpenID Connect \(OIDC\). Follow the procedure relevant for your user category and cloud management tools:

    -   For business users, see [Establish Trust and Federation Between UAA and Identity Authentication](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/161f8f0cfac64c4fa2d973bc5f08a894.html)

    -   For platform users \[Feature Set B\], see [Establish Trust and Federation of Custom Identity Providers for Platform Users \[Feature Set B\]](https://help.sap.com/docs/btp/sap-business-technology-platform/establish-trust-and-federation-of-custom-identity-providers-for-platform-users?version=Cloud)


2.  Provision business and platform users from your identity provider to SAP BTP at a subaccount level. In SAP Cloud Identity Services administration console, configure your source and target systems.

    -   For source system, see [Identity Authentication](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/e4e25f1fae094c2a89ad62159e1cd230.html?version=Cloud)

    -   For target system, see [SAP BTP XS Advanced UAA \(Cloud Foundry\)](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/ecddce6d325e41b49089d4f3a2ce9a18.html?version=Cloud)


    Provisioning business users to SAP BTP, ABAP environment requires setting up the Identity Authentication as a source system and ABAP environment as a target system.

    -   For source system, see [Identity Authentication](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/e4e25f1fae094c2a89ad62159e1cd230.html?version=Cloud)

    -   For target system, see [SAP BTP ABAP environment](https://help.sap.com/docs/identity-provisioning/identity-provisioning/target-sap-btp-abap-environment?version=Cloud)

    -   For end-to-end scenario, see [Provision Users into your SAP BTP ABAP Environment tutorial](https://developers.sap.com/tutorials/abap-environment-ips.html#3afbdef6-09be-431e-a800-2cea45922f5a)


    > ### Note:  
    > If your scenario involves integration with an application running on SAP BTP, such as SAP Build Work Zone, advanced or standard edition, check if Identity Provisioning provides a dedicated connector for it in [Supported Systems](https://help.sap.com/docs/identity-provisioning/identity-provisioning/supported-systems).
    > 
    > If a connector is supported for your application, you will need to configure it as a target system in SAP Cloud Identity Services admin console and connect it to the Identity Authentication source system. Thus, in addition to ensuring application login \(following step 1 above\) and identity lifecycle to your users, you will provision the Global User ID to the local user store of the application. The correlation attribute uniquely identifies a user across SAP business applications and services, as described in [Global User ID in Integration Scenarios](global-user-id-in-integration-scenarios-a04611d.md).

    > ### Note:  
    > Identity Provisioning allows you to connect one source system \(for example, Identity Authentication\) to multiple target systems. This way, with one run of a read or resync job, you can replicate users and groups to all configured target systems.

3.  Once your users are provisioned to your multi-environment subaccounts, you need to map them to their authorizations in SAP BTP. Get familiar with the different use cases described in [Working with Users](https://help.sap.com/docs/btp/sap-business-technology-platform/working-with-users?version=Cloud).

    -   [Assign Users to Role Collections](https://help.sap.com/docs/btp/sap-business-technology-platform/assign-users-to-role-collections?version=Cloud)

    -   [Map Role Collections to User Groups](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/51acfc82c0c54db59de0a528f343902c.html)

    -   [User groups in Identity Authentication](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/ddd067c899f94e2f9006cc4dd417be80.html)





<a name="loio0c3b5dc775794703b57ed7b01f679e45__section_hkr_2g4_fvb"/>

## Neo Subaccounts

1.  Establish the trust between your SAP BTP, Neo subaccount and your Identity Authentication tenant. For more information, see [Integrating the Service with SAP Business Technology Platform, Neo Environment](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/fe84459e688c43698591d3b9e1aac828.html?version=Cloud)

2.  Provision business and platform users from your identity provider to SAP BTP at a subaccount level. In SAP Cloud Identity Services administration console, configure your source and target systems.

    -   For source system, see [Identity Authentication](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/e4e25f1fae094c2a89ad62159e1cd230.html?version=Cloud)

    -   For target system, see [SAP BTP Account Members \(Neo\)](https://help.sap.com/docs/identity-provisioning/identity-provisioning/target-sap-btp-account-members-neo?version=Cloud)

    -   For target system, see [SAP BTP Java/HTML5 apps \(Neo\)](https://help.sap.com/docs/identity-provisioning/identity-provisioning/target-sap-btp-java-html5-apps-neo?version=Cloud)


    > ### Note:  
    > Identity Provisioning allows you to connect one source system \(for example, Identity Authentication\) to multiple target systems. This way, with one run of a read or resync job, you can replicate users and groups to all configured target systems.

3.  Once your users are provisioned to your Neo subaccounts, you need to map them to their authorizations in SAP BTP.

    -   For predefined platform roles, see [Managing Member Authorizations in the Neo Environment](https://help.sap.com/docs/btp/sap-btp-neo-environment/managing-member-authorizations-in-neo-environment?version=Cloud)

    -   For access to Java applications, see [Managing Roles](https://help.sap.com/docs/BTP/ea72206b834e4ace9cd834feed6c0e09/db8175b9d976101484e6fa303b108acd.html?version=Cloud).

    -   For access to HTML5 applications, see [Managing Roles and Permissions](https://help.sap.com/docs/BTP/ea72206b834e4ace9cd834feed6c0e09/d128e6796cf94bb187d4bbf69419e2f5.html?version=Cloud).



**Related Information**  


[Best Practices for SAP BTP](https://help.sap.com/docs/btp/best-practices/best-practices-for-sap-btp?version=Cloud)

