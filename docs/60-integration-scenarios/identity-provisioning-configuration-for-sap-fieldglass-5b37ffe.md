<!-- loio5b37ffea62154b4d9c6ac08bd3e75cbd -->

# Identity Provisioning Configuration for SAP Fieldglass

Set up the systems for your provisioning scenario and run the provisioning jobs.



<a name="loio5b37ffea62154b4d9c6ac08bd3e75cbd__prereq_th3_rkt_krb"/>

## Prerequisites

-   The Identity Provisioning tenant is created for your organization by opening an incident to *BC-IAM-IPS* component.

-   Configuration tasks in Identity Authentication have been completed.




<a name="loio5b37ffea62154b4d9c6ac08bd3e75cbd__context_x43_tl4_rsb"/>

## Context

When your Identity Provisioning tenant is created by opening an incident, your source and target systems are not preconfigured.

Administrators can add source and target systems supported by the service for their provisioning scenarios. They need to configure the connection details and the authentication mechanism for setting up the communication, as well as filtering, conflict resolution and other properties \(if needed\). For more information, follow the procedure described for your provisioning systems: [Source Systems](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/58033bec92124ef2a7905b37d0f50704.html) and [Target Systems](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/ab3f641552464c79b94d10b9205fd721.html)

Newly added systems in the Identity Provisioning admin console are created with the default transformation.



## Procedure

1.  Log on to the Identity Provisioning admin console with your S-user.

    The S-user specified in the incident request is assigned as the initial administrator of the Identity Provisioning tenant.

2.  Set up the source and target systems for your provisioning scenario. For example:

    -   [Identity Authentication \(Source\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/e4e25f1fae094c2a89ad62159e1cd230.html)

    -   [SAP Fieldglass \(Target\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/c4d3fd59a4dd4e7eac783107991afb57.html)


3.  Configure connection and authentication properties for the systems.

4.  Define properties to further control how user data is provisioned. For more information, see: [List of Properties](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/d6f3577f30ec4af98e734b0126a60e37.html), where you need to search for properties prefixed with *<scim\>*.

5.  Review the system transformations. Normally, customers add conditions and functions in the transformations to filter out user data. For more information, see: [Transformations](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/81f5204a5829429781d9ecc8b171f287.html)

6.  Run a provisioning job manually or set a time interval for scheduled jobs. For more information, see: [Start and Stop Provisioning Jobs](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/531a2615b2d04eb8ba46a638b6d81cdc.html)

7.  Monitor the provisioning job. For more information, see: [View Provisioning Job Logs](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/e5b5176c17ae4ae4bd32ae07877ddd79.html)


