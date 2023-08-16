<!-- loioef38d9ee3f7544d882dc3f8de123ad3d -->

# SAP Concur Integration Scenario

Integrating SAP Concur with SAP Cloud Identity Services - Identity Authentication and Identity Provisioning enables user authentication to SAP Concur and user synchronization between the cloud-based travel and expense management solution and Identity Authentication.



<a name="loioef38d9ee3f7544d882dc3f8de123ad3d__section_o1z_m5f_tsb"/>

## Overview

Every person in your organization, who enters or approves expense claims, invoices or authorization requests is a user of SAP Concur. Customers of SAP Concur can use Identity Authentication and Identity Provisioning to automate the identity lifecycle and access management of those users for the cloud-based solution.

New customers typically configure Identity Authentication as a source system, where users are self-registered, uploaded from files, or provisioned by Identity Provisioning from existing user stores, such as Microsoft AD, AS ABAP, or SAP SuccessFactors. Users are then replicated to SAP Concur target systems.

SAP Cloud Identity Services - Identity Authentication and Identity Provisioning, play a key role in further integration between SAP Concur and SAP BTP applications, like SAP Task Center. They provide the option to generate and distribute or use your own Global User ID - the attribute that uniquely identifies a user across system landscape and serves as a prerequisite for the adoption of SAP Task Center. For more information, see [Global User ID in Integration Scenarios](global-user-id-in-integration-scenarios-a04611d.md)



<a name="loioef38d9ee3f7544d882dc3f8de123ad3d__section_qgg_p5f_tsb"/>

## How to Use

After purchasing SAP Concur, the Identity Authentication and Identity Provisioning bundle tenants are automatically created and provisioned for your organization. However, both tenants are not preconfigured. You need to manually configure them for your authentication and provisioning scenarios.

1.  Configure integration between Identity Authentication and SAP Concur.

    Set up the trust between Identity Authentication and SAP Concur. Decide whether Identity Authentication will be configured as the identity provider \(IdP\) for SAP Concur or you will use your own IdP, and therefore configure Identity Authentication as a proxy for authentication. For more information, see the Identity Authentication documentation:

    -   [Configure Applications](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/61ad3b0796ca4f5bae706632a29b1418.html)

    -   [Configure Trust](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/f96e4c5930a94d1ba117e05a3f3c30fc.html)

    -   [Configure Corporate Identity Providers](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/19f3eca47db643b6aad448b5dc1075ad.html)


    For more information about setting up Single Sign-On for your users, see *Section 13: Appendix - SAP Identity Authentication Service \(IAS\) Setup* in [Single Sign-On Setup Guide](https://www.concurtraining.com/customers/tech_pubs/Docs/_Current/SG_Shr/Shr_SG_SSO_Mgmt.pdf)

2.  Configure integration between Identity Provisioning and SAP Concur for user provisioning and distribution of SAP Global User ID.

    For more information, see SAP Concur documentation: [Configure an SAP Concur Entity as an IdP Target](https://www.concurtraining.com/customers/tech_pubs/Docs/_Current/SG_Shr/Shr_SG_Concur_IdP_Target.pdf)

    Create new users in Identity Authentication and provision them to SAP Concur. You can do this using any of the following options: self-register users, upload them from CSV files, provision them by Identity Provisioning from existing user stores, such as Microsoft AD, AS ABAP, SAP SuccessFactors. For more information, see:

    -   [User Management](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/228428f9f476449cafd841a68d75b234.html?version=Cloud)

    -   [Identity Authentication \(Source\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/e4e25f1fae094c2a89ad62159e1cd230.html)

    -   [SAP Concur \(Target\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/032fd80fd7de4e4992402637b77c1f2c.html)


    Provision users from SAP Concur to Identity Authentication. Configure SAP Concur source system and Identity Authentication target system in the Identity Provisioning admin console and run or schedule a provisioning job. For more information, see:

    -   [SAP Concur \(Source\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/209ea8281e6d49b28d85f87e5b2120fe.html)

    -   [Identity Authentication \(Target\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/f217bd39c17d47cdb4f89ed19cb2c701.html)



**Related Information**  


[Scenario Setup](../40-scenario-setup/scenario-setup-ae9137c.md "When an SAP cloud solution bundles with SAP Cloud Identity Services, you are entitled to receive Identity Authentication and Identity Provisioning tenants without additional costs on the purchase of the corresponding SAP cloud solution's license. These Identity Authentication and Identity Provisioning tenants come preconfigured with the SAP cloud solution.")

