<!-- loioae915d60107447f397b3de1a1cd498f5 -->

# Scenario Requirements

To set up your SAP cloud solutions to use the SAP Cloud Identity Services - Identity Authentication and Identity Provisioning, make sure you meet the following requirements:

-   You've purchased one of the SAP cloud solutions which bundle Identity Authentication and Identity Provisioning services:

    -   SAP SuccessFactors

    -   SAP S/4HANA Cloud

    -   SAP Fieldglass

    -   SAP Concur

    -   SAP Ariba

    -   SAP Cloud for Customers


    You've purchased an SAP on-premise solution:

    -   SAP S/4HANA \(also valid for SAP S/4HANA Cloud, private edition\)

        SAP S/4HANA on-premise edition doesn't bundle Identity Authentication and Identity Provisioning. To use the SAP Cloud Identity Services for authentication and provisioning scenarios with SAP S/4HANA on-premise, purchase an SAP cloud solution that bundles both services then reuse and configure their tenants.


-   You've obtained your Identity Authentication and Identity Provisioning bundle tenants.

    > ### Note:  
    > Effective October 20, 2020, Identity Provisioning is offered bundled with SAP cloud solutions. You can obtain and use it, along with Identity Authentication, as part of a bundled SAP cloud solution that you need to purchase. The service is no longer sold as a stand-alone product. Existing customers of standalone Identity Provisioning can use it as-is until the end of their contracts. For more information, see [Standalone Tenants](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/552fef99dd2c48629305221490b2b12c.html)

    > ### Note:  
    > Effective March 15, 2022, new Identity Provisioning bundle tenants are created on the infrastructure of SAP Cloud Identity Services only. Existing customers of bundle tenants on SAP BTP, Neo environment can migrate them to the common infrastructure of Identity Authentication and Identity Provisioning or continue using them as-is. For more information, see [Migrate Identity Provisioning Tenant](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/055f92d5e11d491c97b68223c68179ad.html?version=Cloud)

    -   SAP SuccessFactors

        Creating Identity Authentication and Identity Provisioning tenants is triggered through an upgrade process in SAP SuccessFactors Upgrade Center. After the upgrade process completes, an e-mail is sent with tenant details and login information. For more information, see: [Getting Started with Identity Authentication and SAP SuccessFactors](https://help.sap.com/viewer/568fdf1f14f14fd089a3cd15194d19cc/Latest/en-US/35c74e4605564a82a5be6c7fdadf9aef.html) 

    -   SAP S/4HANA Cloud release 1911 and higher

        Creating Identity Authentication and Identity Provisioning tenants is triggered automatically. You receive onboarding e-mails with the URL links to your Identity Authentication and Identity Provisioning tenants. For more information, see:

        -   [Identity Authentication: Tenant Model and Licensing](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/93160ebd2dcb40e98aadcbb9a970f2b9.html) → *Getting a Tenant* → *Many SAP cloud products automatically trigger a tenant delivery if a default tenant isn’t yet provisioned*

        -   [SAP S/4HANA Cloud Bundle](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/01b30d0f96f94243acf272b2f414b3a7.html) → *You have purchased the product after release 1911*

        -   [SAP S/4HANA Cloud Bundle](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/01b30d0f96f94243acf272b2f414b3a7.html) → *You have purchased the product before release 1911*


    -   SAP Fieldglass

        As SAP Fieldglass currently don't bundle Identity Authentication, you either need to purchase the service and obtain a tenant or use an existing one. Creating the Identity Provisioning tenant for SAP Fieldglass is triggered manually by opening an incident. For more information, see: [SAP Fieldglass Bundle](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/1b299f67d20845a2aee57902fdbc3755.html?version=Cloud) → *How to Obtain*

    -   SAP Concur

        You receive onboarding e-mails with the URL links to your Identity Authentication and Identity Provisioning tenants.

    -   SAP Ariba

        New customers of SAP Ariba receive onboarding e-mails with the URL links to your Identity Authentication and Identity Provisioning tenants. Existing customers of SAP Ariba obtain bundle tenants by opening an incident. For more information, see [SAP Ariba Applications Bundle](https://help.sap.com/docs/IDENTITY_PROVISIONING/9b86e4081f744be1a7c4dd915cfbf370/672f97aaaacd421ead344b396b1e8bd8.html?state=DRAFT) → *How to Obtain*

    -   SAP S/4HANA \(also valid for SAP S/4HANA Cloud, private edition\)

        The SAP S/4HANA on-premise edition is enabled as a source, target, and proxy system \(connector\) in all Identity Provisioning bundle tenants. After purchasing an SAP cloud solution that bundles Identity Authentication and Identity Provisioning, you can use SAP S/4HANA On-Premise connector for your provisioning and authentication scenarios. Configurations for SAP S/4HANA are applicable for SAP S/4HANA Cloud, private edition.


    > ### Note:  
    > Customers can view their Identity Authentication and Identity Provisioning tenants by accessing the *SAP Cloud Identity Services - Tenants* application at the following URL: [https://iamtenants.accounts.cloud.sap/](https://iamtenants.accounts.cloud.sap/). The application displays the following information:
    > 
    > -   Type of tenant \(test or productive\)
    > 
    > -   Date of creation
    > 
    > -   Region
    > 
    > -   Tenant administrators


**Related Information**  


[Identity Authentication: Tenant Model and Licensing](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/93160ebd2dcb40e98aadcbb9a970f2b9.html)

[Identity Provisioning: Tenant Model](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/65fa74998ef14f059806f0c5a48e5285.html)

