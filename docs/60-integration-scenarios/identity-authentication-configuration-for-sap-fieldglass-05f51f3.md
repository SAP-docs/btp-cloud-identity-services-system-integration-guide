<!-- loio05f51f3128124693a1da0faf503060c6 -->

# Identity Authentication Configuration for SAP Fieldglass

Configure Identity Authentication to use SAML 2.0 single sign-on \(SSO\), username and password login, two-factor authentication, and other login options to control access your SAP Fieldglass systems.



<a name="loio05f51f3128124693a1da0faf503060c6__context_zmd_nck_4rb"/>

## Context

> ### Tip:  
> In bundled scenarios, SAP Fieldglass systems come with a preconfigured Identity Authentication tenant. You've received a provisioning e-mail with initial access information for Identity Authentication. **The steps presented here are for a manual configuration only.**



<a name="loio05f51f3128124693a1da0faf503060c6__steps_gjb_55q_lrb"/>

## Procedure

1.  Download the SAML metadata from the tenant settings configuration of your Identity Authentication tenant.

    For more information, see [Configuring Tenant Settings](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/e81a19b0067f4646982d7200a8dab3ca.html?version=Cloud) in the documentation for Identity Authentication.

    Copy the signing certificate to a file and export the public key.

    1.  From the *Signing Certificate* section, copy the text form of the certificate from the *Insert as Text* field and save it to a file.

        For example: `my_tenant_signing_cert.cer`.

    2.  Open the certificate file and export the public key.

        On Microsoft Windows computers, you can open the file with Crypto Shell Extension, choose the *Details* tab, select the public key, and choose *Copy to File …*.

        After exporting the public key, you've a file like `public_key_my_tenant_signing_cert.cer`.


2.  Create an app for your SAP Fieldglass solution.

    For more information, see [Create SAML 2.0 application](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/fe3102ad92d94baa955ffa06b86d2cfa.html?version=Cloud) in the documentation for Identity Authentication.

3.  Configure SAP Fieldglass for single sign-on.

    1.  To enable single sign-on, upload the SAML metadata from your Identity Authentication tenant.

    2.  Download the SAML metadate of your SAP Fieldglass tenant.


    For more information, see [Single Sign-On](https://help.sap.com/viewer/73c0a1be6aaa46ef9b66b1c3f28a77f4/cloud/en-US/3ea269afd914434e91c292896da56272.html) in the documentation of SAP Fieldglass.

4.  Trust SAP Fieldglass as a service provider.

    For more information, see [Configure SAML 2.0 Service Provider](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/51f1f7550dc24aa99cbf84d1e96e2ad5.html?version=Cloud) in the documentation for Identity Authentication.

    After uploading the service provider metadata, the fields are populated with the parsed data from the XML file. The minimum required configuration is to complete the *Name* field.

5.  Consider any optional configurations for your application in Identity Authentication

    For more information, see [Scenario Setup](../40-scenario-setup/scenario-setup-ae9137c.md).


