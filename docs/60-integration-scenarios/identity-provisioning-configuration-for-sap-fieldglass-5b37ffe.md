<!-- loio5b37ffea62154b4d9c6ac08bd3e75cbd -->

# Identity Provisioning Configuration for SAP Fieldglass

Set up the systems for your provisioning scenario and run the provisioning jobs.



<a name="loio5b37ffea62154b4d9c6ac08bd3e75cbd__prereq_th3_rkt_krb"/>

## Prerequisites

-   The technical contact person in your organization has received the welcome e-mails from SAP with the tenant URL and the login information.

-   > ### Tip:  
    > In bundled scenarios, SAP Fieldglass comes with a preconfigured source and target systems. You can use them as-is and run provisioning jobs or you can further adjust their configurations according to your needs. For more information, see [SAP Fieldglass Bundle](https://help.sap.com/docs/identity-provisioning/identity-provisioning/sap-fieldglass-bundle). **The steps presented here are for a manual configuration only.**




<a name="loio5b37ffea62154b4d9c6ac08bd3e75cbd__context_x43_tl4_rsb"/>

## Context



<a name="loio5b37ffea62154b4d9c6ac08bd3e75cbd__steps_lft_t3r_pzb"/>

## Procedure

1.  Sign in to the administration console of SAP Cloud Identity Services and navigate to *Identity Provisioning*.

    For more information, see [Access Identity Provisioning UI of Bundle Tenants](https://help.sap.com/docs/identity-provisioning/identity-provisioning/access-identity-provisioning-ui-of-bundle-tenants?version=Cloud)

2.  Review your preconfigured source and target systems.

    When opening the admin console, the *System Name* of the source and the target system is populated, and the *Properties* are preconfigured. You can adjust them according to your needs. For example, you can add filtering properties to control the provisioned data, enable bulk operations, if supported and others. For more information, see [List of Properties](https://help.sap.com/docs/identity-provisioning/identity-provisioning/list-of-properties).

3.  Review the transformations of the preconfigured source and target systems.

    You can use the default source and target system transformations. However, you may want to modify them by adding conditions, functions and additional transformation code to further control how SAP Fieldglass user data is received in Identity Authentication, for example.

4.  At this point, you can schedule, run and monitor a provisioning job.

    For more information, see [Start and Stop Provisioning Jobs](https://help.sap.com/docs/identity-provisioning/identity-provisioning/start-and-stop-provisioning-jobs?version=Cloud).

5.  \(Optional\) Configure additional source, target and proxy systems supported by the service for your scenarios as described in [Supported Systems](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/81ca0c1b51b449daac240a18ee0d3ab1.html).


