<!-- loio5e37165632bb4597aa26d362d8621745 -->

# Third-Party Scenarios

Integrating third-party systems with SAP Cloud Identity Services - Identity Authentication and Identity Provisioning enables user authentication to the third-party system and user synchronization between the third-party system and Identity Authentication.

> ### Remember:  
> You're charged for every successful authentication to SAP Cloud Identity Services from a third-party application regardless of the protocol used. Only logon requests coming from an SAP cloud or SAP on-premise application are free of charge.
> 
> For more information, see [Licensing and Usage](https://help.sap.com/docs/identity-authentication/identity-authentication/tenant-model-and-licensing).

> ### Restriction:  
> Identity Provisioning only supports a limited set of third-party target systems and then only for standalone tenants or bundle tenants with the *SAP Identity Access Governance bundle* option. Identity Provisioning supports third-party source and proxy systems for all tenant types. If your third-party system isn't among those systems supported by Identity Provisioning or if you don't have the required tenant type, then you must find alternative methods for provisioning data between Identity Authentication and your system. Such methods include the use of SCIM APIs to read data from Identity Directory, the persistence layer of Identity Authentication.
> 
> For a list of supported connectors for Identity Provisioning, see [Target Systems](https://help.sap.com/docs/identity-authentication/identity-authentication/target-systems) in the SAP Cloud Identity Services documentation.



<a name="loio5e37165632bb4597aa26d362d8621745__section_cpd_pjc_n1c"/>

## Overview

Customers of third-party systems can use Identity Authentication and Identity Provisioning to automate the identity lifecycle and access management of the third-party system users.

Identity Authentication and Identity Provisioning play a key role in further integration between the third-party system and SAP Business Technology Platform applications, like SAP Task Center. They provide the option to generate and distribute or use your own Global User ID - the attribute that uniquely identifies a user across the system landscape and serves as a prerequisite for the adoption of SAP Task Center.

For more information, see [Global User ID in Integration Scenarios](global-user-id-in-integration-scenarios-a04611d.md).



<a name="loio5e37165632bb4597aa26d362d8621745__section_vtl_3mc_n1c"/>

## How to Use

Currently, there are no third-party bundles with SAP Cloud Identity Services - Identity Authentication and Identity Provisioning. We don't offer standalone tenants of Identity Provisioning for purchase anymore. Therefore, to integrate the third-party solution with both services, you need to purchase an SAP cloud solution, which bundles with Identity Authentication and Identity Provisioning. This solution could be, for example, SAP S/4HANA Cloud, SAP SuccessFactors, Identity Access Governance, or any other bundled solution listed under [Bundles](https://help.sap.com/docs/identity-authentication/identity-authentication/bundles) section. As a result, you’ll get Identity Authentication and Identity Provisioning tenants preconfigured for the purchased solution.

To distribute users with Global User ID to the third-party solution, use the relevant Identity Provisioning connector for your third-party system if there's one available and your tenant type and bundle option supports it. If there's no connector available, you must use your own solution for distributing user data. SAP Cloud Identity Services provides SCIM APIs for programmatic access to the system. For more information, see [SAP Cloud Identity Services](https://api.sap.com/package/SCPIdentityServices/rest) on the *SAP Business Accelerator Hub*.

To configure the integration between the third-party system and SAP Cloud Identity Services, proceed as follows:

1.  Configure integration between Identity Authentication and the third-party system.

    Set up the trust between Identity Authentication and the third-party system. Decide whether Identity Authentication will be configured as the identity provider \(IdP\) for the third-party system or you'll use your own IdP, and therefore configure Identity Authentication as a proxy for authentication. Identity Authentication supports OpenID Connect and SAML. For more information, see the Identity Authentication documentation:

    -   [Configure Applications](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/61ad3b0796ca4f5bae706632a29b1418.html)

    -   [Configure Trust](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/f96e4c5930a94d1ba117e05a3f3c30fc.html)

    -   [Configure Corporate Identity Providers](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/19f3eca47db643b6aad448b5dc1075ad.html)


2.  Configure user provisioning and distribution of SAP Global User ID. You have the following options:

    -   Use Identity Provisioning.

        Typical scenario for new customers \(greenfield scenario\) - Create new users in Identity Authentication and provision them to the third-party system. You can do this using any of the following options: self-register users, upload them from CSV files, or provision them with Identity Provisioning from existing user stores, such as Microsoft AD, AS ABAP, SAP SuccessFactors. For more information, see:

        -   [User Management](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/228428f9f476449cafd841a68d75b234.html?version=Cloud)

        -   [Identity Authentication \(Target\)](https://help.sap.com/docs/identity-authentication/identity-authentication/identity-authentication-f217bd39c17d47cdb4f89ed19cb2c701)

        -   [Identity Authentication \(Source\)](https://help.sap.com/docs/identity-authentication/identity-authentication/identity-authentication-e4e25f1fae094c2a89ad62159e1cd230)

        -   Use a target connector for the third-party system if one is available. See [Target Systems](https://help.sap.com/docs/identity-authentication/identity-authentication/target-systems).


        Typical scenario for existing customers \(brownfield scenario\) - Provision users from the third-party system to Identity Authentication. Configure the third-party source system and Identity Authentication target system in the admin console and run or schedule a provisioning job. For more information, see:

        -   Use a source connector for the third-party system if one is available. See [Source Systems](https://help.sap.com/docs/identity-authentication/identity-authentication/source-systems).

        -   [Identity Authentication \(Target\)](https://help.sap.com/docs/identity-authentication/identity-authentication/identity-authentication-f217bd39c17d47cdb4f89ed19cb2c701)


    -   Use a third-party tool and SCIM APIs to provision user data between systems.

        For more information, see [SAP Cloud Identity Services](https://api.sap.com/package/SCPIdentityServices/rest) on the *SAP Business Accelerator Hub*.



As a result, the provisioned users are able to log in to the third-party system using single sign-on. If Identity Authentication is configured as the identity provider, the service is used for authentication. If Identity Authentication is configured to use a corporate IdP, the service acts as a proxy and delegates the authentication request to this corporate IdP.

