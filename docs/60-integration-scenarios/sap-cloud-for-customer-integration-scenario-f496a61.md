<!-- loiof496a6156c35497cadd2ed7fb6e326d2 -->

# SAP Cloud for Customer Integration Scenario

Integrating SAP Cloud for Customer \(also known as SAP Sales Cloud and SAP Service Cloud\) with SAP Cloud Identity Services - Identity Authentication and Identity Provisioning enables user authentication to SAP Cloud for Customer and user synchronization between the cloud-based solution that helps you manage day-to-day sales and service interactions and Identity Authentication.



<a name="loiof496a6156c35497cadd2ed7fb6e326d2__section_hyn_njh_g5b"/>

## Overview

Customers of SAP Cloud for Customer can use Identity Authentication and Identity Provisioning to automate the identity lifecycle and access management of SAP Cloud for Customer users.

Identity Authentication and Identity Provisioning play a key role in further integration between SAP Cloud for Customer and SAP Business Technology Platform applications, like SAP Task Center. They provide the option to generate and distribute or use your own Global User ID - the attribute that uniquely identifies a user across system landscape and serves as a prerequisite for the adoption of SAP Task Center. For more information, see: [Global User ID in Integration Scenarios](global-user-id-in-integration-scenarios-a04611d.md)



<a name="loiof496a6156c35497cadd2ed7fb6e326d2__section_qgg_p5f_tsb"/>

## How to Use

Currently, SAP Cloud for Customer does not bundle with SAP Cloud Identity Services - Identity Authentication and Identity Provisioning. Therefore, to integrate the cloud-based solution with both services, you need to purchase an SAP cloud solution, other than SAP Cloud for Customer, which bundles them. This could be, for example, SAP S/4HANA Cloud, SAP SuccessFactors or any other bundled solution listed under [Bundle Tenants and Connectors](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/5db6c8dcf7a347fe81e2a78c3df9ec50.html?version=Cloud) section. As a result, you will get Identity Authentication and Identity Provisioning tenants preconfigured for the purchased solution.

Also, to use Identity Provisioning for distributing users with Global User ID to SAP Cloud for Customer, your Identity Provisioning tenant must run on SAP Cloud Identity infrastructure. This way you will be able to use the SAP Cloud for Customer connector. In case your tenant is running on SAP BTP, Neo environment, you need to migrate first, as described in [Migrate Identity Provisioning Tenant](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/055f92d5e11d491c97b68223c68179ad.html?version=Cloud).

Last but not least, you need to manually configure the integration between SAP Cloud for Customer and SAP Cloud Identity Services. Proceed as follows:

1.  Configure integration between Identity Authentication and SAP Cloud for Customer.

    Set up the trust between Identity Authentication and SAP Cloud for Customer. Decide whether Identity Authentication will be configured as the identity provider \(IdP\) for SAP Cloud for Customer or you will use your own IdP, and therefore configure Identity Authentication as a proxy for authentication. For more information, see the Identity Authentication documentation:

    -   [Configure Applications](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/61ad3b0796ca4f5bae706632a29b1418.html)

    -   [Configure Trust](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/f96e4c5930a94d1ba117e05a3f3c30fc.html)

    -   [Configure Corporate Identity Providers](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/19f3eca47db643b6aad448b5dc1075ad.html)


    For more information, see [Setting Up Trust Between Identity Authentication and SAP Cloud for Customer](https://help.sap.com/docs/BTP/65de2977205c403bbc107264b8eccf4b/2903a3cf69444140832d4c365c808385.html)

2.  Configure integration between Identity Provisioning and SAP Cloud for Customer for user provisioning and distribution of SAP Global User ID.

    Create new users in Identity Authentication and provision them to SAP Cloud for Customer. You can do this using any of the following options: self-register users, upload them from CSV files, provision them by Identity Provisioning from existing user stores, such as Microsoft AD, AS ABAP, SAP SuccessFactors. For more information, see:

    -   [User Management](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/228428f9f476449cafd841a68d75b234.html?version=Cloud)

    -   [Identity Authentication \(Source\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/e4e25f1fae094c2a89ad62159e1cd230.html)

    -   [SAP Sales Cloud and SAP Service Cloud \(Target\)](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/1a974bcb1e6b4a6ebd5078e81ebf7875.html?version=Cloud)


    Provision users from SAP Cloud for Customer to Identity Authentication. Configure SAP Cloud for Customer source system and Identity Authentication target system in the Identity Provisioning admin console and run or schedule a provisioning job. For more information, see:

    -   [SAP Sales Cloud and SAP Service Cloud \(Source\)](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/8f3edc371dff4c749714702974cd1e48.html?version=Cloud)

    -   [Identity Authentication \(Target\)](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/f217bd39c17d47cdb4f89ed19cb2c701.html)


    For more information, see [Identity Provisioning in SAP Cloud for Customer using System for Cross-Domain Identity Management \(SCIM\)](https://help.sap.com/docs/SAP_CLOUD_FOR_CUSTOMER/b5196c50731249cdb877bd3b44d9f48d/30727bdccd6a4646aa7087bebd783ecd.html?version=CLOUD)


