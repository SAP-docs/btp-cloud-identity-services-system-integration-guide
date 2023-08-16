<!-- loio7fbca9bcb55e42babe8cf76b6bf77ce3 -->

# Identity Provisioning Configuration for SAP S/4HANA

Set up the systems for your provisioning scenario and run the provisioning jobs. Configurations for SAP S/4HANA are applicable for SAP S/4HANA Cloud, private edition.



<a name="loio7fbca9bcb55e42babe8cf76b6bf77ce3__prereq_th3_rkt_krb"/>

## Prerequisites

-   You've purchased an SAP cloud solution bundled with Identity Authentication and Identity Provisioning.

    The SAP S/4HANA on-premise edition is enabled as source, target, and proxy systems \(connectors\) in all Identity Provisioning bundle tenants.

-   You have installed the Cloud Connector in your corporate environment and have done the initial configuration.




<a name="loio7fbca9bcb55e42babe8cf76b6bf77ce3__steps_nkf_vfx_krb"/>

## Procedure

1.  Log on to the Identity Provisioning admin console with your administrator credentials.

2.  Set up the source and target systems for your provisioning scenario.

    For the purposes of this scenario, you need to add Identity Authentication as a source system and SAP AS ABAP and SAP S/4HANA as target systems in the Identity Provisioning UI.

    -   [Identity Authentication \(Source\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/e4e25f1fae094c2a89ad62159e1cd230.html)

    -   [SAP Application Server ABAP \(Target\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/7a0c6e7f67f5456fab32a34a252f4399.html)

    -   [SAP S/4HANA On-Premise \(Target\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/fd6de3ccee3e4ca09ed49b6c7d8c0042.html)


3.  Run a provisioning job manually or set a time interval for scheduled jobs. For more information, see: [Start and Stop Provisioning Jobs](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/531a2615b2d04eb8ba46a638b6d81cdc.html)

    > ### Note:  
    > This scenario requires that you first provision the Identity Authentication users to SAP AS ABAP and then to SAP S/4HANA.

4.  Monitor the provisioning job. For more information, see: [View Provisioning Job Logs](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/e5b5176c17ae4ae4bd32ae07877ddd79.html)


