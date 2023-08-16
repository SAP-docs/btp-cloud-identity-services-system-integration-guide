<!-- loio8ce83db434934ce894235e4a448db987 -->

# SAP SuccessFactors Integration Scenario

Integrating SAP SuccessFactors with SAP Cloud Identity Services -Identity Authentication and Identity Provisioning enables user authentication to SAP SuccessFactors and user synchronization between the cloud-based human resource \(HR\) solution and Identity Authentication.



<a name="loio8ce83db434934ce894235e4a448db987__section_wld_sfj_3rb"/>

## Overview

In a typical scenario, new users \(employees\) are created in SAP SuccessFactors and provisioned to Identity Authentication.

-   If Identity Authentication is configured as the identity provider \(IdP\), the provisioned users receive activation e-mails to set their password for accessing the SAP SuccessFactors application.

-   If Identity Authentication is configured to use a corporate IdP for authentication, the service acts as a proxy and delegates the authentication request to this corporate IdP.


When the users are replicated to Identity Authentication, the service becomes the leading system for user provisioning. In Identity Provisioning admin console, Identity Authentication can be configured as a source system itself for reading and replicating the user data to one or multiple target systems in your landscape.

SAP Cloud Identity Services - Identity Authentication and Identity Provisioning, play a key role in further integration between SAP SuccessFactors and SAP BTP applications, like SAP Task Center. They provide the option to generate and distribute or use your own Global User ID - the attribute that uniquely identifies a user across system landscape and serves as a prerequisite for the adoption of SAP Task Center. For more information, see [Global User ID in Integration Scenarios](global-user-id-in-integration-scenarios-a04611d.md)



<a name="loio8ce83db434934ce894235e4a448db987__section_vrw_n2h_rsb"/>

## How to Use

The upgrade process in SAP SuccessFactors Upgrade Center preconfigures the Identity Authentication and Identity Provisioning bundle tenants.

In Identity Authentication admin console, an application is created and connected to the SAP SuccessFactors instance where your users will log on to. Also, the trust properties are configured. However, you can review those configurations and edit them if necessary.

For more information on how to set up Identity Authentication, see: [Identity Authentication Configuration for SAP SuccessFactors](identity-authentication-configuration-for-sap-successfactors-5c96ada.md)

Once you complete your configuration in Identity Authentication, you can go on with your provisioning tasks in Identity Provisioning admin console. Your SAP SuccessFactors source and Identity Authentication target systems are configured, and you are ready to run a provisioning job. The provisioning service reads the user data from SAP SuccessFactors, transforms it as needed and writes the data to Identity Authentication.

For more information on how to set up Identity Provisioning, see: [Identity Provisioning Configuration for SAP SuccessFactors](identity-provisioning-configuration-for-sap-successfactors-24c9293.md)

-   **[Identity Authentication Configuration for SAP SuccessFactors](identity-authentication-configuration-for-sap-successfactors-5c96ada.md "Configure Identity
                                Authentication to
		use SAML 2.0 single sign-on (SSO), username and password login, two-factor authentication,
		and other login options to control access your SAP SuccessFactors systems.")**  
Configure Identity Authentication to use SAML 2.0 single sign-on \(SSO\), username and password login, two-factor authentication, and other login options to control access your SAP SuccessFactors systems.
-   **[Identity Provisioning Configuration for SAP SuccessFactors](identity-provisioning-configuration-for-sap-successfactors-24c9293.md "Set up the systems for your provisioning scenario and run the provisioning
		jobs.")**  
Set up the systems for your provisioning scenario and run the provisioning jobs.

