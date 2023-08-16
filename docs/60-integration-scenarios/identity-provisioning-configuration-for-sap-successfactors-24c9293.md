<!-- loio24c929304fb84ec3a2fee3ca87edcf87 -->

# Identity Provisioning Configuration for SAP SuccessFactors

Set up the systems for your provisioning scenario and run the provisioning jobs.



<a name="loio24c929304fb84ec3a2fee3ca87edcf87__prereq_th3_rkt_krb"/>

## Prerequisites

> ### Note:  
> If your SAP SuccessFactors tenant was created after December 9, 2022, Identity Authentication and Identity Provisioning have already been enabled and are using Mutual Transport Layer Security \(mTLS\) in conjunction with the System for Cross-domain Identity Management \(SCIM\) API, which are the latest methods of authentication and integration with Identity Authentication and Identity Provisioning. You do not need to initiate the upgrade to SAP Cloud Identity Services - Identity Authentication in the SAP SuccessFactors *Upgrade Center*.
> 
> For more information, see [Initiating the Upgrade to SAP Cloud Identity Services - Identity Authentication Service](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/568fdf1f14f14fd089a3cd15194d19cc/0271d9c4176e45ca9307e49230073240.html?version=latest).



## Procedure

1.  Log on to the Identity Provisioning admin console.

2.  Review your *SAP SuccessFactors* source and *Identity Authentication* target system configurations.

    When opening the Identity Provisioning admin console, the *System Name* of the source and the target system is populated and the *Properties* are preconfigured.

    You need to make some adjustments to the existing properties configuration, as described here: [Setting Up the Identity Provisioning Source and Target Systems](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/568fdf1f14f14fd089a3cd15194d19cc/6efee5906dc6422285d16cbaccaf203c.html?version=latest)

3.  Review your *SAP SuccessFactors* source and *Identity Authentication* target system transformations.

    You can use the default source and target system transformations. However, you may want to modify them by adding conditions, functions and additional transformation code to further control how SAP SuccessFactors user data is received in Identity Authentication. Common changes include: migrating passwords from SAP SuccessFactors to Identity Authentication, removing duplicate emails, defining whether you want users to receive email notifications when they’re created in Identity Authentication.

    For more information on the various cases you may want to modify the source and target transformations, see: [Configure Transformations in SAP Cloud Identity Services - Identity Provisioning](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/568fdf1f14f14fd089a3cd15194d19cc/19ecea22faed41888c7f2afc82fa8ee4.html?version=latest)

4.  At this point, you can run and monitor a provisioning job.

    For more information, see: [Running and Scheduling Jobs \(User Sync\)](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/568fdf1f14f14fd089a3cd15194d19cc/02f401d638bd42e49fb7d39565189c3e.html?version=latest) and [View Provisioning Job Logs](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/e5b5176c17ae4ae4bd32ae07877ddd79.html)

5.  \(Optional\) Configure additional source, target and proxy systems supported by the service for your scenarios as described in [Supported Systems](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/81ca0c1b51b449daac240a18ee0d3ab1.html).

    For more information on how to use the service for user provisioning in default and proxy mode, see the Identity Provisioning section in [Scenario Setup](../40-scenario-setup/scenario-setup-ae9137c.md)


