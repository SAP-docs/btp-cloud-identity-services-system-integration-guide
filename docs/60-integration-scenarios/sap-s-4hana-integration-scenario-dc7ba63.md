<!-- loiodc7ba639647d4ddaa88874eb7656dff1 -->

# SAP S/4HANA Integration Scenario

Integrating SAP S/4HANA with SAP Cloud Identity Services -Identity Authentication and Identity Provisioning or SAP Identity Management enables user authentication to SAP S/4HANA and user synchronization between the SAP S/4HANA family and Identity Authentication.



<a name="loiodc7ba639647d4ddaa88874eb7656dff1__section_wld_sfj_3rb"/>

## Overview

In a typical scenario, users are created in Identity Authentication \(self-registered, uploaded from files or provisioned from another source system via Identity Provisioning\) and replicated to SAP S/4HANA using either Identity Provisioning, or SAP Identity Management.

Both Identity Provisioning and SAP Identity Management can manage business partners linked to business users in SAP S/4HANA when the integration with a human resource \(HR\) system, such as SAP HCM and SAP SuccessFactors, is inactive. In SAP S/4HANA, a business user is a natural person who is represented by a business partner and a link to a user in the system. A business user can also be defined as a SU01 user who has a one-to-one relation to the corresponding business partner.

-   **Identity Provisioning scenario**

    This scenario requires that you first provision the users from Identity Authentication to SAP AS ABAP and then replicate them to SAP S/4HANA. This will ensure that business partners created in SAP S/4HANA are linked to the relevant business users.

    In the Identity Provisioning admin console, you need to configure Identity Authentication as a source system, and SAP S/4HANA and SAP AS ABAP as target systems.

-   **SAP Identity Management scenario**

    This scenario requires that you configure the following SAP Identity Management connectors: Identity Authentication \(that is, SCI\), SAP S/4HANA and SAP AS ABAP \(or SAP BusinessSuite\).

    Users are loaded from Identity Authentication to SAP Identity Management by running the *SCI* initial load job for the Identity Authentication repository. Afterwards, they are assigned the SAP AS ABAP and the S/4HANA account privileges and provisioned to SAP S/4HANA.

    The SAP AS ABAP \(or SAP BusinessSuite\) and SAP S/4HANA connectors are used to manage the business partners linked to the business users. The link is handled by the SAP Identity Management attribute MX\_S4HANA\_USERASSIGNMENT\_USERID. Its value is the LogonUID of the SU01 user to which the business partner is linked. The SAP AS ABAP connector provisions the SU01 user to SAP S/4HANA, where it is created as a *User with Classic Address*. Following a provisioning of the same user by the SAP S/4HANA connector, it is linked to the business partner and becomes a *User with Business Partner Assignment*.

    It is important that SAP S/4HANA connector is always used along with the SAP AS ABAP or the BusinessSuite connector, as this will ensure data synchronization between SAP Identity Management, SAP S/4HANA and SAP AS ABAP


SAP Cloud Identity Services - Identity Authentication and Identity Provisioning, play a key role in further integration between SAP S/4HANA and SAP BTP applications, like SAP Task Center. They provide the option to generate and distribute or use your own Global User ID - the attribute that uniquely identifies a user across system landscape and serves as a prerequisite for the adoption of SAP Task Center. For more information, see [Global User ID in Integration Scenarios](global-user-id-in-integration-scenarios-a04611d.md)



<a name="loiodc7ba639647d4ddaa88874eb7656dff1__section_tzl_n3m_rrb"/>

## How to Use

You need to configure your Identity Authentication and Identity Provisioning tenants for integration scenarios with SAP S/4HANA as described in [Identity Authentication Configuration for SAP S/4HANA](identity-authentication-configuration-for-sap-s-4hana-3b99d58.md#loio3b99d58a5ca644028e8ef5a04dc215ad) and [Identity Provisioning Configuration for SAP S/4HANA](identity-provisioning-configuration-for-sap-s-4hana-7fbca9b.md).

For integration scenarios with SAP Identity Management, refer to [SAP Identity Management Configuration for SAP S/4HANA](sap-identity-management-configuration-for-sap-s-4hana-5333b00.md).

-   **[Identity Authentication Configuration for SAP S/4HANA](identity-authentication-configuration-for-sap-s-4hana-3b99d58.md#loio3b99d58a5ca644028e8ef5a04dc215ad "Configure Identity
                                Authentication to
		use SAML 2.0 single sign-on (SSO), username and password login, two-factor authentication,
		and other login options to control access your SAP S/4HANA
		systems")**  
Configure Identity Authentication to use SAML 2.0 single sign-on \(SSO\), username and password login, two-factor authentication, and other login options to control access your SAP S/4HANA systems
-   **[Identity Provisioning Configuration for SAP S/4HANA](identity-provisioning-configuration-for-sap-s-4hana-7fbca9b.md "Set up the systems for your provisioning scenario and run the provisioning jobs.
		Configurations for SAP S/4HANA are applicable for SAP S/4HANA Cloud, private
		edition.")**  
Set up the systems for your provisioning scenario and run the provisioning jobs. Configurations for SAP S/4HANA are applicable for SAP S/4HANA Cloud, private edition.
-   **[SAP Identity Management Configuration for SAP S/4HANA](sap-identity-management-configuration-for-sap-s-4hana-5333b00.md "Set up the systems for your provisioning scenario with SAP Identity Management and run
		the initial load jobs.")**  
Set up the systems for your provisioning scenario with SAP Identity Management and run the initial load jobs.

