<!-- loio9114a3590c1a4f8f8de926f18add29f1 -->

# SAP Ariba Integration Scenario

Integrating SAP Ariba with SAP Cloud Identity Services - Identity Authentication and Identity Provisioning enables user authentication to SAP Ariba and user synchronization between the cloud-based procurement and supply chain solution and Identity Authentication.



<a name="loio9114a3590c1a4f8f8de926f18add29f1__section_hyn_njh_g5b"/>

## Overview

Customers of SAP Ariba can use Identity Authentication and Identity Provisioning to automate the identity lifecycle and access management of SAP Ariba users.

Identity Authentication and Identity Provisioning play a key role in further integration between SAP Ariba and SAP Business Technology Platform applications, like SAP Task Center. They provide the option to generate and distribute or use your own Global User ID - the attribute that uniquely identifies a user across system landscape and serves as a prerequisite for the adoption of SAP Task Center. For more information, see:

-   [Global User ID in Integration Scenarios](global-user-id-in-integration-scenarios-a04611d.md)

-   [User authentication and single sign-on using the SAP Cloud Identity Services – Identity Authentication service](https://help.sap.com/docs/ARIBA_PROCUREMENT/e10ed2159560487bb36d1ae89a6e293a/0d87d5f302c34590a9bb2d83cf22b9b7.html)




<a name="loio9114a3590c1a4f8f8de926f18add29f1__section_iv4_4jh_g5b"/>

## How to Use

Currently, SAP Ariba does not bundle with SAP Cloud Identity Services - Identity Authentication and Identity Provisioning. Therefore, in order to integrate the cloud-based procurement and supply chain solution with both services, you need to purchase an SAP cloud solution, other than SAP Ariba, which bundles with Identity Authentication and Identity Provisioning. This could be, for example, SAP S/4HANA Cloud, SAP SuccessFactors or any other bundled solution listed under [Bundle Tenants and Connectors](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/5db6c8dcf7a347fe81e2a78c3df9ec50.html?version=Cloud) section. As a result, you will get Identity Authentication and Identity Provisioning tenants preconfigured for the purchased solution.

To distribute users with Global User ID to SAP Ariba you need to use the Identity Provisioning connector for SAP Ariba Applications. This connector is enabled only for Identity Provisioning tenants running on the SAP Cloud Identity Services infrastructure. In case your tenant is running on SAP BTP, Neo environment, you need to migrate first, as described in [Migrate Identity Provisioning Tenant](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/055f92d5e11d491c97b68223c68179ad.html?version=Cloud).

> ### Note:  
> The following procedure is not applicable for SAP Business Network \(formerly known as SAP Ariba Network\), which has its own dedicated connector in Identity Provisioning.

To configure the integration between SAP Ariba and SAP Cloud Identity Services, proceed as follows:

1.  Configure integration between Identity Authentication and SAP Ariba.

    Set up the trust between Identity Authentication and SAP Ariba. Decide whether Identity Authentication will be configured as the identity provider \(IdP\) for SAP Ariba or you will use your own IdP, and therefore configure Identity Authentication as a proxy for authentication. For more information, see the Identity Authentication documentation:

    -   [Configure Applications](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/61ad3b0796ca4f5bae706632a29b1418.html)

    -   [Configure Trust](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/f96e4c5930a94d1ba117e05a3f3c30fc.html)

    -   [Configure Corporate Identity Providers](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/19f3eca47db643b6aad448b5dc1075ad.html)


    You can also refer to the [Configuring Trust with IAS and SAP Ariba: Step by Step Instructions](https://blogs.sap.com/2022/02/01/configuring-trust-with-ias-and-sap-ariba-step-by-step-instructions/) blog post.

2.  Configure user provisioning and distribution of SAP Global User ID. You have the following options:

    -   Use Identity Provisioning.

        > ### Note:  
        > The SAP Ariba Applications source and target systems consume SCIM 2.0 API provided by the cloud-based procurement and supply chain solution. For more information about the SAP Ariba SCIM API scope of support, see SAP Note [3228340](https://me.sap.com/notes/3228340).

        Typical scenario for new SAP Ariba customers \(greenfield scenario\) - Create new users in Identity Authentication and provision them to SAP Ariba. You can do this using any of the following options: self-register users, upload them from CSV files, provision them by Identity Provisioning from existing user stores, such as Microsoft AD, AS ABAP, SAP SuccessFactors. For more information, see:

        -   [User Management](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/228428f9f476449cafd841a68d75b234.html?version=Cloud)

        -   [Identity Authentication \(Target\)](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/f217bd39c17d47cdb4f89ed19cb2c701.html)

        -   [Identity Authentication \(Source\)](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/e4e25f1fae094c2a89ad62159e1cd230.html)

        -   [SAP Ariba Applications \(Target\)](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/47c890311337469e8615de705c54b3f4.html)


        Typical scenario for existing SAP Ariba customers \(brownfield scenario\) - Provision users from SAP Ariba to Identity Authentication. Configure SAP Ariba Applications source system and Identity Authentication target system in the Identity Provisioning admin console and run or schedule a provisioning job. For more information, see:

        -   [SAP Ariba Applications \(Source\)](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/0ef109106be242319bb18ac4130a9564.html)

        -   [Identity Authentication \(Target\)](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/f217bd39c17d47cdb4f89ed19cb2c701.html)


    -   Use existing SAP Ariba APIs.

        Provision users by using OData API and file upload.



As a result, the provisioned users should be able to login to SAP Ariba using single sign-on. If Identity Authentication is configured as the identity provider, the service is used for authentication. If Identity Authentication is configured to use a corporate IdP, the service acts as a proxy and delegates the authentication request to this corporate IdP.

