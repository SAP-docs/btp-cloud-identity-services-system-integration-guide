<!-- loioc0b3041d08ca4ec686ecb9841088993d -->

# SAP Fieldglass Integration Scenario

Integrating SAP Fieldglass with SAP Cloud Identity Services -Identity Authentication and Identity Provisioning enables user authentication to SAP Fieldglass and user synchronization between the cloud-based, open vendor management system \(VMS\) and Identity Authentication.



<a name="loioc0b3041d08ca4ec686ecb9841088993d__section_wld_sfj_3rb"/>

## Overview

SAP Fieldglass distinguishes between users and external workers. A user in SAP Fieldglass is a full-time employee of the organization who utilizes the application for the management of external workers \(also known as contingent workers, contractors, freelancers\).

Users can log on to SAP Fieldglass application to complete business tasks. They are normally created in the HR solution of the organization \(for example, SAP SuccessFactors\), managed by Identity Authentication, and provisioned to SAP Fieldglass via Identity Provisioning.

In a typical scenario, users are created in Identity Authentication \(self-registered, uploaded from files or provisioned via Identity Provisioning from another source system\) and replicated to SAP Fieldglass.

> ### Note:  
> Users that require access to SAP Fieldglass, are managed in Identity Authentication, with Identity Authentication being configured as a source system for reading and transferring the employee user data to SAP Fieldglass. Within SAP Fieldglass the ability to create a new user is no longer available and the ability to edit a user has restrictions around which attributes can be updated.

If Identity Authentication is configured as the identity provider \(IdP\), the provisioned users receive activation emails to set the password for accessing their SAP Fieldglass application. If a corporate IdP is configured for authentication, Identity Authentication acts as a proxy and delegates the authentication request to this corporate IdP.

SAP Cloud Identity Services - Identity Authentication and Identity Provisioning, play a key role in further integration between SAP Fieldglass and SAP BTP applications, like SAP Task Center. They provide the option to generate and distribute or use your own Global User ID - the attribute that uniquely identifies a user across system landscape and serves as a prerequisite for the adoption of SAP Task Center. For more information, see [Global User ID in Integration Scenarios](global-user-id-in-integration-scenarios-a04611d.md)



<a name="loioc0b3041d08ca4ec686ecb9841088993d__section_ub5_3y2_tsb"/>

## How to Use

After purchasing your SAP Fieldglass, the Identity Provisioning tenant is created for your organization by opening an incident to *BC-IAM-IPS* component. To use an Identity Authentication tenant, you either need to purchase the service and obtain a tenant or use an existing one.

You need to configure both tenants, as described in [Identity Authentication Configuration for SAP Fieldglass](identity-authentication-configuration-for-sap-fieldglass-05f51f3.md#loio05f51f3128124693a1da0faf503060c6) and [Identity Provisioning Configuration for SAP Fieldglass](identity-provisioning-configuration-for-sap-fieldglass-5b37ffe.md).

-   **[Identity Authentication Configuration for SAP Fieldglass](identity-authentication-configuration-for-sap-fieldglass-05f51f3.md#loio05f51f3128124693a1da0faf503060c6 "Configure Identity
                                Authentication to
		use SAML 2.0 single sign-on (SSO), username and password login, two-factor authentication,
		and other login options to control access your SAP Fieldglass
		systems.")**  
Configure Identity Authentication to use SAML 2.0 single sign-on \(SSO\), username and password login, two-factor authentication, and other login options to control access your SAP Fieldglass systems.
-   **[Identity Provisioning Configuration for SAP Fieldglass](identity-provisioning-configuration-for-sap-fieldglass-5b37ffe.md "Set up the systems for your provisioning scenario and run the provisioning jobs. ")**  
Set up the systems for your provisioning scenario and run the provisioning jobs.

