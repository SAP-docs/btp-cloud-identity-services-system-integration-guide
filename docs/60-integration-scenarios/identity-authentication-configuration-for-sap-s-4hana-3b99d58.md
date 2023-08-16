<!-- loio3b99d58a5ca644028e8ef5a04dc215ad -->

# Identity Authentication Configuration for SAP S/4HANA

Configure Identity Authentication to use SAML 2.0 single sign-on \(SSO\), username and password login, two-factor authentication, and other login options to control access your SAP S/4HANA systems



## Procedure

1.  [Get the SAML Metadata of Your Identity Authentication Tenant](identity-authentication-configuration-for-sap-s-4hana-3b99d58.md#loio5cdd1c9ca9a546bb9c4a44ab7077866b)

2.  [Create an App for Your SAP S/4HANA Solution](identity-authentication-configuration-for-sap-s-4hana-3b99d58.md#loio98ed592546b64144bb9ec0c5a7d55ad3)

3.  [Enable the ABAP Platform as an SAML Service Provider](identity-authentication-configuration-for-sap-s-4hana-3b99d58.md#loioe5d471fe524a401181dc3edcdecf3868)

4.  [Trust Identity Authentication as an Identity Provider](identity-authentication-configuration-for-sap-s-4hana-3b99d58.md#loio5a1e6bbd78a04812ac22e7bdce8bac2b)

5.  [Set the Name ID Format for Your ABAP Platform Client](identity-authentication-configuration-for-sap-s-4hana-3b99d58.md#loiofbc900a77f9a4548bd3962bf9982a633)

6.  [Trust the ABAP Platform Client as a Service Provider](identity-authentication-configuration-for-sap-s-4hana-3b99d58.md#loio4c113ee2ddcf44639997fc6beb97a08b)

7.  [Configuring the Subject Name Identifier Consumed by the ABAP Platform](identity-authentication-configuration-for-sap-s-4hana-3b99d58.md#loioc89001c4943642c79927a0e591cc0bc7)


<a name="loio5cdd1c9ca9a546bb9c4a44ab7077866b"/>

<!-- loio5cdd1c9ca9a546bb9c4a44ab7077866b -->

## Get the SAML Metadata of Your Identity Authentication Tenant

As the administrator of the Identity Authentication tenant, get the SAML metadata for the identity provider.



<a name="loio5cdd1c9ca9a546bb9c4a44ab7077866b__steps_ssz_vcg_rrb"/>

## Procedure

1.  Access the tenant's administration console for Identity Authentication by using the console's URL.

    > ### Note:  
    > The URL has the following pattern:
    > 
    > <code>https://<i class="varname">&lt;tenant ID&gt;</i>.accounts.ondemand.com/admin</code>
    > 
    > *Tenant ID* is an automatically generated ID by the system. The first administrator created for the tenant receives an activation e-mail with a URL in it. This URL contains the *tenant ID*.
    > 
    > If you've a configured custom domain, the URL has the <code><i class="varname">&lt;your custom domain&gt;</i>/admin pattern</code>.

2.  Under *Applications & Resources*, choose the *Tenant Settings* tile.

3.  Choose the *SAML 2.0 Configuration* list item.

4.  Choose *Download Metadata File*.

5.  From the *Signing Certificate* section, copy the text form of the certificate from the *Insert as Text* field and save it to a file.

    For example: `my_tenant_signing_cert.cer`.

6.  Open the certificate file and export the public key.

    On Microsoft Windows computers, you can open the file with Crypto Shell Extension, choose the *Details* tab, select the public key, and choose *Copy to File …*

    After exporting the public key, you've a file like `public_key_my_tenant_signing_cert.cer`.


<a name="loio98ed592546b64144bb9ec0c5a7d55ad3"/>

<!-- loio98ed592546b64144bb9ec0c5a7d55ad3 -->

## Create an App for Your SAP S/4HANA Solution

As the administrator of the Identity Authentication tenant, create an Identity Authentication application to represent the SAP S/4HANA system.



<a name="loio98ed592546b64144bb9ec0c5a7d55ad3__steps_aqm_jdg_rrb"/>

## Procedure

1.  Under *Applications & Resources*, choose the *Applications* tile.

2.  Choose the *Create* button.

3.  Enter the required information.

    Set the *Application Type* to `SAP on-premise Solution`.

4.  Save your entries.


<a name="loioe5d471fe524a401181dc3edcdecf3868"/>

<!-- loioe5d471fe524a401181dc3edcdecf3868 -->

## Enable the ABAP Platform as an SAML Service Provider

As the administrator of your ABAP Platform client, enable the client as an SAML 2.0 service provider.



<a name="loioe5d471fe524a401181dc3edcdecf3868__steps_ppx_5dg_rrb"/>

## Procedure

1.  Open *SAML 2.0 Configuration* \(transaction `SAML2`\).

    If your ABAP client has never been configured for SAML, you see the message ***Client "*<Client\_Id\>*" is not configured to support SAML 2.0***.

    To enable the configuration, choose *Enable SAML 2.0 Support* \> *Create SAML 2.0 Local Provider*.

2.  Enter a name for the provider.

3.  Continue through the configuration wizard and enter data as desired.

4.  Choose Finish.

    Once enabled, you can configure the bindings supported by the service provider, trust an identity provider, configure identity federation, and protect resources with SAML. The configuration creates 2 Secure Store and Forward \(SSF\) applications and associates Personal Security Environment \(PSE\) files with them. The PSE files contain the signing and encryption key pairs of the service provider.

5.  Choose *Metadata*.

    Save the metadata to a file, such as `abap_client_metadata.xml`.

6.  Activate the required Internet Communication Framework \(ICF\) services.

    To use the service provider, activate the following ICF services:

    -   `/default_host/sap/public/bc/sec/saml2`

    -   `/default_host/sap/public/bc/sec/cdc_ext_service`



<a name="loio5a1e6bbd78a04812ac22e7bdce8bac2b"/>

<!-- loio5a1e6bbd78a04812ac22e7bdce8bac2b -->

## Trust Identity Authentication as an Identity Provider

As the administrator of your ABAP Platform client, configure your client to trust the Identity Authentication tenant as an identity provider.



## Procedure

1.  Open *SAML 2.0 Configuration* \(transaction `SAML2`\).

2.  Choose the *Trusted Providers* tab.

3.  Choose *Add* \> *Upload Metadata File*.

4.  Select the metadata file you downloaded from your Identity Authentication tenant for upload and choose *Next*.

5.  With the *Upload from File* option, select the public key certificate you extracted from the signing certificate of your Identity Authentication tenant and choose *Next*.

6.  Finish the configuration wizard for trusted providers.

    For more information, see [Trusting an Identity Provider](https://help.sap.com/viewer/f118a8960caf41808bd374e28a834f58/latest/en-US/4ab6e4323fec6d83e10000000a42189c.html) in the ABAP Platform documentation for your release.


<a name="loiofbc900a77f9a4548bd3962bf9982a633"/>

<!-- loiofbc900a77f9a4548bd3962bf9982a633 -->

## Set the Name ID Format for Your ABAP Platform Client

As the administrator of your ABAP Platform client, configure a name ID format for your client to accept.



## Context

To share information about a user, partners must be able to identify the user, even though they may use different identifiers for the same user. The SAML 2.0 standard defines the name identifier \(name ID\) as the means to establish a common identifier.

For more information, see [Identity Federation in AS ABAP](https://help.sap.com/viewer/f118a8960caf41808bd374e28a834f58/latest/en-US/f4a4aa9a3f9e47e09f5cc2eeb017c1ec.html) in the documentation of your ABAP Platform version.



## Procedure

1.  Open *SAML 2.0 Configuration* \(transaction `SAML2`\).

2.  Choose the *Trusted Providers* tab.

3.  Select the trusted provider that represents your Identity Authentication tenant and choose Edit.

4.  Under *Details of Identity Provider "*<Identity\_Provider\_Name\>*"*, choose the *Identity Federation* tab.

5.  Choose *Add*.

6.  Choose a name ID format and choose *OK*.

    The name ID format you choose must match the format configured for the ABAP Platform client by the administrator of the Identity Authentication. \(See also [Configuring the Subject Name Identifier Consumed by the ABAP Platform](identity-authentication-configuration-for-sap-s-4hana-3b99d58.md#loioc89001c4943642c79927a0e591cc0bc7).\) This setting defines the format that the ABAP Platform expects the attribute sent in the SAML assertion to be in.

    > ### Example:  
    > Typically, an SAML assertion uses an e-mail address, logon alias, or other user name. Set the name ID format to *Unspecified* or *Email*.

7.  Under *Details of NameID Format "*<NameID\_Format\>*"*, set *User ID Mapping Mode*.

    In this step, you configure how the name ID in the SAML assertion is mapped to the local user in the ABAP Platform. Through this mapping, the ABAP Platform identifies who is logging on. The information provided in the SAML assertion should match 1:1 with a single user in the ABAP Platform.

    > ### Example:  
    > To continue the previous example, configure the ABAP Platform to map the assertion to an e-mail address, logon alias, or user name of the user record. The *User ID Source* is the name ID itself and *User ID Mapping Mode* maps the name ID to *Logon ID*, *Alias* or *Email*.

8.  Save your entries.


<a name="loio4c113ee2ddcf44639997fc6beb97a08b"/>

<!-- loio4c113ee2ddcf44639997fc6beb97a08b -->

## Trust the ABAP Platform Client as a Service Provider

As the administrator of your Identity Authentication tenant, configure your tenant to trust the ABAP Platform client as a service provider.



## Procedure

1.  Access the tenant's administration console for Identity Authentication by using the console's URL.

    > ### Note:  
    > The URL has the following pattern:
    > 
    > <code>https://<i class="varname">&lt;tenant ID&gt;</i>.accounts.ondemand.com/admin</code>
    > 
    > *Tenant ID* is an automatically generated ID by the system. The first administrator created for the tenant receives an activation e-mail with a URL in it. This URL contains the *tenant ID*.
    > 
    > If you've a configured custom domain, the URL has the <code><i class="varname">&lt;your custom domain&gt;</i>/admin pattern</code>.

2.  Under *Applications & Resources*, choose the *Applications* tile.

3.  Select the application you created for your ABAP Platform client.

4.  Under the *Trust* tab, choose *SAML 2.0 Configuration*.

5.  Upload the service provider metadata XML file.

    > ### Note:  
    > Use a file with a `.xml` extension.

    On upload of the metadata of the service provider, the fields are populated with the parsed data from the XML file. The minimum required configuration is to complete the *Name* field.

6.  Save your entries.


<a name="loioc89001c4943642c79927a0e591cc0bc7"/>

<!-- loioc89001c4943642c79927a0e591cc0bc7 -->

## Configuring the Subject Name Identifier Consumed by the ABAP Platform

The Subject Name Identifier is a profile attribute that Identity Authentication sends to the application as name ID in the SAML 2.0 assertions, and as subject in the OpenID Connect tokens. The application then uses this attribute to identify the user.



## Context

> ### Note:  
> When the application uses a corporate identity provider for authentication, the use of the Identity Authentication user store is disabled, the Subject Name Identifier attribute configurations in the administration console for Identity Authentication aren't relevant. In such scenarios Identity Authentication sends to the application the Subject Name Identifier attribute that comes from the corporate identity provider without changing it.
> 
> For more information about the corporate identity provider scenario, see [Corporate Identity Providers](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/19f3eca47db643b6aad448b5dc1075ad.html) and [Configure Identity Federation](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/c029bbbaefbf4350af15115396ba14e2.html) in the Identity Authentication documentation.



<a name="loioc89001c4943642c79927a0e591cc0bc7__steps_jmc_d52_4qb"/>

## Procedure

1.  Access the tenant's administration console for Identity Authentication by using the console's URL.

    > ### Note:  
    > The URL has the following pattern:
    > 
    > <code>https://<i class="varname">&lt;tenant ID&gt;</i>.accounts.ondemand.com/admin</code>
    > 
    > *Tenant ID* is an automatically generated ID by the system. The first administrator created for the tenant receives an activation e-mail with a URL in it. This URL contains the *tenant ID*.
    > 
    > If you've configured custom domain, the URL has the <code><i class="varname">&lt;your custom domain&gt;</i>/admin pattern</code>.

2.  Under *Applications & Resources*, choose the *Applications* tile.

3.  Select the application you created for your ABAP Platform client.

4.  Under the *Trust* tab, choose *Subject Name Identifier*.

5.  For the basic attribute, select the attribute to use to log on to the ABAP Platform.

    Negotiate with the administrator of the ABAP Platform which attribute to use for logon to the ABAP Platform service provider. \(See also [Set the Name ID Format for Your ABAP Platform Client](identity-authentication-configuration-for-sap-s-4hana-3b99d58.md#loiofbc900a77f9a4548bd3962bf9982a633).\) The ABAP Platform maps the value provided in the attribute to a single user of the ABAP Platform to enable log on.

6.  Save your entries.


