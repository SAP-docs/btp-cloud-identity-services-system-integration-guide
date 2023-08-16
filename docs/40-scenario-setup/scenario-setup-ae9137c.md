<!-- loioae9137c0aaa94f92a9ea133c28905f92 -->

# Scenario Setup

When an SAP cloud solution bundles with SAP Cloud Identity Services, you are entitled to receive Identity Authentication and Identity Provisioning tenants without additional costs on the purchase of the corresponding SAP cloud solution's license. These Identity Authentication and Identity Provisioning tenants come preconfigured with the SAP cloud solution.



<a name="loioae9137c0aaa94f92a9ea133c28905f92__section_rwz_3r4_psb"/>

## 1. Set Up Identity Authentication

After purchasing an SAP cloud solution, the technical contact person in your organization receives a welcome e-mail. The contact person is specified in the Order Form for SAP Cloud Services. We create a user account for Identity Authentication for the contact person. The contact person is the first administrator in the administration console for Identity Authentication. This person receives an activation e-mail for the administration console account. The subject of the e-mail is: *Activate Your Account for Administration Console*.

1.  Follow the required steps and activate your account.

2.  Start the administration console for Identity Authentication.

    The URL has the pattern <code>https://<i class="varname">&lt;tenant_ID&gt;</i>.accounts.ondemand.com/admin</code>.

    The *tenant ID* is generated automatically by the system. The URL and tenant ID are in the activation e-mail received by the first administrator.

    > ### Caution:  
    > Only the technical contact person is added as administrator of Identity Authentication. This person can add other administrators and assign roles. For more information about how to add new administrators in Identity Authentication, see [Add User as Administrator](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/bbbdbdd3899942ce874f3aae9ba9e21d.html?q=Add%20Administrators#loio1dc498bff0674743a1a3a0ec3f0bf298).

3.  Normally, bundle tenants are preconfigured. An application is created and connected to the SAP cloud solution where your users log on. Trust properties are also configured. You can further customise your configurations to define login methods and rules, such as conditional authentication, risk-based authentication, single sign-on and others.

    For more information, see Identity Authentication [Operation Guide](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/6a8e67cf98bf41968ea2849dfd0b6bbd.html). Configure Identity Authentication so users can have all enhanced features for each scenario:

    1.  Add additional administrators or edit the administrator roles. For more information, see [Add Administrators](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/bbbdbdd3899942ce874f3aae9ba9e21d.html#loiobbbdbdd3899942ce874f3aae9ba9e21d) and [Edit Administrator Authorizations](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/86ee37423f8945a1898faff1e6308756.html).

    2.  Create new applications. For more information, see [Creating a new Application.](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/0d4b255051c74955a959146beee4bd8c.html).

    3.  Configure trust between your applications and Identity Authentication. For more information, see [Configuring Trust](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/f96e4c5930a94d1ba117e05a3f3c30fc.html).



In the administration console, administrators can configure Identity Authentication so that users can have all enhanced features for each scenario. For more information about the configuration options in Identity Authentication, see [Operation Guide](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/6a8e67cf98bf41968ea2849dfd0b6bbd.html).



<a name="loioae9137c0aaa94f92a9ea133c28905f92__section_qxs_kr4_psb"/>

## 2. Set Up Identity Provisioning

After purchasing an SAP cloud solution, the technical contact person in your organization receives a welcome e-mail. This person is has administrator permissions for the bundle tenant and performs the initial logon by accessing the tenant URL provided in the e-mail.

1.  Access your Identity Provisioning bundle tenant URL and log on with your administrator credentials.

    For more information, see [Access Identity Provisioning UI of Bundle Tenants](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/7ab5884ffbc44461a57622d2f633e57c.html)

2.  Start using the service for your provisioning scenarios in default and/or proxy mode.

    Follow the procedure under *How to Use Bundle Tenants* section in [Bundle Tenants and Connectors](https://help.sap.com/docs/IDENTITY_PROVISIONING/f48e822d6d484fa5ade7dda78b64d9f5/5db6c8dcf7a347fe81e2a78c3df9ec50.html).


