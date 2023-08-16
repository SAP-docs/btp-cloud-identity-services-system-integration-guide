<!-- loio93102ca17e184bfda453852a20ca9d93 -->

# SAP S/4HANA Cloud Integration Scenario

Integrating SAP S/4HANA Cloud with SAP Cloud Identity Services - Identity Authentication and Identity Provisioning enables user authentication to SAP S/4HANA Cloud and SAP Analytics Cloud, embedded edition and user synchronization between Identity Authentication, SAP S/4HANA Cloud and SAP Analytics Cloud.



<a name="loio93102ca17e184bfda453852a20ca9d93__section_ujs_dww_krb"/>

## Overview

In a typical scenario, users are created in Identity Authentication \(self-registered, uploaded from files or provisioned via Identity Provisioning from another source system, such as SAP SuccessFactors\) and replicated to SAP S/4HANA Cloud. From there, users are provisioned to the embedded SAP Analytics Cloud. As a result, when they log on to SAP S/4HANA Cloud, they are enabled to view and work with embedded SAP Analytics Cloud stories and data analyzer reports within SAP S/4HANA Cloud without the need to log on twice.

-   If Identity Authentication is configured as the identity provider \(IdP\), the provisioned users are authenticated by the service when accessing SAP S/4HANA Cloud and SAP Analytics Cloud applications.

-   If Identity Authentication is configured to use a corporate IdP for authentication, the service acts as a proxy and delegates the authentication request to this corporate IdP.


In scenarios where SAP S/4HANA Cloud is configured as a target system, the integration with a human resource \(HR\) system is active and cannot be switched off. In this case, the synchronization of business partners is managed by the HR system and SAP S/4HANA Cloud. Identity Provisioning can't be used for creating and managing business partners in SAP S/4HANA Cloud. Instead, it can only be used for managing business users \(login users and their login information\) and their role assignments.

SAP S/4HANA Cloud distinguishes between business users and business partners as follows:

**Business partners** are the central master data objects that hold the complete person profile in the SAP S/4HANA Cloud. For example, business partners for employees, customers, or suppliers.

**Business users** are persons who can log on to SAP S/4HANA Cloud system to complete business tasks. A business user is connected to a business partner. It can only be created in S/4HANA Cloud if a business partner for this person exists. A business partner can exist in SAP S/4HANA Cloud without a business user, meaning with no access to SAP S/4HANA Cloud. For example, a business partner for customer or supplier.

SAP Cloud Identity Services - Identity Authentication and Identity Provisioning, play a key role in further integration between SAP S/4HANA Cloud and SAP BTP applications, like SAP Task Center. They provide the option to generate and distribute or use your own Global User ID - the attribute that uniquely identifies a user across system landscape and serves as a prerequisite for the adoption of SAP Task Center. For more information, see [Global User ID in Integration Scenarios](global-user-id-in-integration-scenarios-a04611d.md)



<a name="loio93102ca17e184bfda453852a20ca9d93__section_jrz_z3g_rsb"/>

## How to Use

After purchasing SAP S/4HANA Cloud release 1911 and higher, Identity Authentication and Identity Provisioning bundle tenants come preconfigured.

> ### Note:  
> If you are using SAP S/4HANA Cloud release lower than 1911, the Identity Provisioning tenant is created for your organization by opening an incident to *XX-S4C-OPR-SRV* *\(S/4HANA Cloud service requests\)* component. Your source and target systems are not preconfigured.

In Identity Authentication admin console, applications are created and connected to the SAP S/4HANA Cloud and SAP Analytics Cloud instances where your users will log on to. Also, the trust between Identity Authentication and both systems is configured. However, you can review those configurations and edit them if necessary.

For more information on how to set up Identity Authentication, see: [Identity Authentication Configuration for SAP S/4HANA Cloud](identity-authentication-configuration-for-sap-s-4hana-cloud-a94abe1.md)

Once you complete your configuration in Identity Authentication, you can go on with your provisioning tasks in Identity Provisioning admin console. Your Identity Authentication and SAP S/4HANA Cloud source systems, as well as SAP S/4HANA Cloud and SAP Analytics Cloud target systems are configured and you are ready to run a provisioning job. The provisioning service reads the user data from Identity Authentication, transforms it as needed and writes the data to SAP S/4HANA Cloud and SAP Analytics Cloud.

For more information on how to set up Identity Provisioning, see: [Identity Provisioning Configuration for SAP S/4HANA Cloud](identity-provisioning-configuration-for-sap-s-4hana-cloud-cc0013a.md)

-   **[Identity Authentication Configuration for SAP S/4HANA Cloud](identity-authentication-configuration-for-sap-s-4hana-cloud-a94abe1.md "")**  

-   **[Identity Provisioning Configuration for SAP S/4HANA Cloud](identity-provisioning-configuration-for-sap-s-4hana-cloud-cc0013a.md "Set up the systems for your provisioning scenario and run the provisioning
		jobs.")**  
Set up the systems for your provisioning scenario and run the provisioning jobs.

