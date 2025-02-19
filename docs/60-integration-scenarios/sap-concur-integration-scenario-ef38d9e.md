<!-- loioef38d9ee3f7544d882dc3f8de123ad3d -->

# SAP Concur Integration Scenario

Integrating SAP Concur with SAP Cloud Identity Services - Identity Authentication and Identity Provisioning enables user authentication to SAP Concur and user synchronization between the cloud-based travel and expense management solution and Identity Authentication.



<a name="loioef38d9ee3f7544d882dc3f8de123ad3d__section_o1z_m5f_tsb"/>

## Overview

Every person in your organization, who enters or approves expense claims, invoices or authorization requests is a user of SAP Concur. Customers of SAP Concur can use Identity Authentication and Identity Provisioning to automate the identity lifecycle and access management of those users for the cloud-based solution. Customers can integrate SAP Cloud Identity Services no matter whether the Concur instance is integrated with their own corporate identity provider or not.

New customers typically configure Identity Authentication as a source system, where users are self-registered, uploaded from files, or provisioned by Identity Provisioning from existing user stores, such as Microsoft AD, AS ABAP, or SAP SuccessFactors. Users are then replicated to SAP Concur target systems.

> ### Restriction:  
> Identity Provisioning can provision core identity information into the SAP Concur solutions. The *Spend* profile information for the user must be updated using the SAP Concur APIs, or the SAP Concur user import. For more information, see [Core Identity Data](https://developer.concur.com/api-reference/profile/v4.1.identity.html#schema-) and [User Provisioning Service](https://developer.concur.com/api-reference/user-provisioning/v4.user-provisioning.html).

SAP Cloud Identity Services - Identity Authentication and Identity Provisioning, play a key role in further integration between SAP Concur and SAP BTP applications, like SAP Task Center. They provide the option to generate and distribute or use your own Global User ID - the attribute that uniquely identifies a user across system landscape and serves as a prerequisite for the adoption of SAP Task Center. For more information, see [Global User ID in Integration Scenarios](global-user-id-in-integration-scenarios-a04611d.md)



<a name="loioef38d9ee3f7544d882dc3f8de123ad3d__section_llr_syg_vzb"/>

## Prerequisites

-   New or existing Concur Expense, Concur Request, Concur Invoice, and/or Concur Travel & Expense customers that have at least one other SAP cloud solution.

    > ### Note:  
    > Concur Travel-only is not currently supported.

-   Identity Authentication and Identity Provisioning tenants must be created or configured by SAP:

    1.  You need to check with your SAP Concur account team to determine if you are eligible for provisioning of a tenant with Identity Authentication and Identity Provisioning services.

    2.  If eligible, create a support case to initiate the provisioning of an SAP Cloud Identity Services tenant with Identity Authentication and Identity Provisioning services. For customers with an existing Identity Authentication and Identity Provisioning tenants, the tenants will be reused.

        > ### Note:  
        > You must create a case to set up Identity Authentication and Identity Provisioning tenant provisioning for your SAP Concur entity even if you already have existing Identity Authentication and Identity Provisioning tenants from other SAP solutions.

        To create a case, you can create an SAP Concur support case \(recommended\) or an SAP for Me case.

        For more information about creating an SAP Concur support case, see the *How to Navigate the SAP Concur Support Portal* section on the [SAP Concur Support](https://assets.concur.com/tech-pubs/SAP-Concur-Training-Library/GTM.htm) page for instructions on creating a support case. Use the Case Type = Single Sign On.

        For more information about creating an SAP for Me case, see this SAP Note: [1296527](https://me.sap.com/notes/1296527) - How to create a support case \(contact SAP Product Support\) - SAP for Me. Use the Component = BNS-CON-SSO.



Once the prerequisites are completed, you can proceed to configure Identity Authentication as single sign-on \(SSO\) for SAP Concur and Identity Provisioning for SAP Concur as a target system from within the SAP Cloud Identity Services administration console, detailed in the *How to Use* section on this page.



<a name="loioef38d9ee3f7544d882dc3f8de123ad3d__section_qgg_p5f_tsb"/>

## How to Use

After the case to initiate the Identity Authentication and Identity Provisioning bundle tenants is complete, you need to manually configure them for your authentication and provisioning scenarios.

1.  Configure integration between Identity Authentication and SAP Concur.

    Set up the trust between Identity Authentication and SAP Concur. Decide whether Identity Authentication will be configured as the identity provider \(IdP\) for SAP Concur or you will use your own IdP, and therefore configure Identity Authentication as a proxy for authentication. For more information, see the Identity Authentication documentation:

    -   [Configure Applications](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/61ad3b0796ca4f5bae706632a29b1418.html)

    -   [Configure Trust](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/f96e4c5930a94d1ba117e05a3f3c30fc.html)

    -   [Configure Corporate Identity Providers](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/19f3eca47db643b6aad448b5dc1075ad.html)


    For more information about setting up Single Sign-On for your users, see [Appendix – SAP Cloud Identity Services - Identity Authentication Service \(SAP IAS\) Setup](https://help.sap.com/docs/SAP_CONCUR/8b1fb4bc53c843c080bcfc4b965366a1/1b82f8af6caf101483b9b0372adb2c3a.html).

2.  Configure integration between Identity Provisioning and SAP Concur for user provisioning and distribution of SAP Global User ID.

    For more information, see SAP Concur documentation: [Configure an SAP Concur Entity as an IdP Target](https://help.sap.com/docs/SAP_CONCUR/83c94f03f949423a8f76158375832747/1b925e2f6caf10148b97b230c1b3e173.html?version=Latest).

    Create new users in Identity Authentication and provision them to SAP Concur. You can do this using any of the following options: self-register users, upload them from CSV files, provision them by Identity Provisioning from existing user stores, such as Microsoft AD, AS ABAP, SAP SuccessFactors. For more information, see:

    -   [User Management](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/228428f9f476449cafd841a68d75b234.html?version=Cloud)

    -   [Identity Authentication \(Source\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/e4e25f1fae094c2a89ad62159e1cd230.html)

    -   [SAP Concur \(Target\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/032fd80fd7de4e4992402637b77c1f2c.html)


    Provision users from SAP Concur to Identity Authentication. Configure SAP Concur source system and Identity Authentication target system in the Identity Provisioning admin console and run or schedule a provisioning job. For more information, see:

    -   [SAP Concur \(Source\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/209ea8281e6d49b28d85f87e5b2120fe.html)

    -   [Identity Authentication \(Target\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/f217bd39c17d47cdb4f89ed19cb2c701.html)





<a name="loioef38d9ee3f7544d882dc3f8de123ad3d__section_pxd_plj_d1c"/>

## Tenant Lifecycle

Tenants of SAP Cloud Identity Services - Identity Authentication and Identity Provisioning go through different phases in their lifecycle. For more information about onboarding and offboarding, see [Tenant Lifecycle](https://help.sap.com/docs/cloud-identity/what-are-sap-cloud-identity-services/tenant-lifecycle?version=Cloud).

**Related Information**  


[Scenario Setup](../40-scenario-setup/scenario-setup-ae9137c.md "When an SAP cloud solution bundles with SAP Cloud Identity Services, you are entitled to receive Identity Authentication and Identity Provisioning tenants without additional costs on the purchase of the corresponding SAP cloud solution's license. These Identity Authentication and Identity Provisioning tenants come preconfigured with the SAP cloud solution.")

