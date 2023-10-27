<!-- loiocc0013a997334a698662267ac34e9502 -->

# Identity Provisioning Configuration for SAP S/4HANA Cloud

Set up the systems for your provisioning scenario and run the provisioning jobs.



<a name="loiocc0013a997334a698662267ac34e9502__prereq_th3_rkt_krb"/>

## Prerequisites

-   If you are using SAP S/4HANA Cloud release 1911 and higher, the Identity Provisioning tenant has been provisioned for your organization.

-   The technical contact person in your organization has received the welcome e-mail from SAP with the tenant URL and the login information.

-   Configuration tasks in Identity Authentication have been completed.




<a name="loiocc0013a997334a698662267ac34e9502__context_k3q_s1m_rsb"/>

## Context



<a name="loiocc0013a997334a698662267ac34e9502__steps_akh_ktm_rsb"/>

## Procedure

1.  Log on to the Identity Provisioning admin console with your administrator credentials.

    When opening the Identity Provisioning admin console, the source and target systems are displayed with the following system names:

    -   <code>IAS for <i class="varname">&lt;s4hana-tenant-id&gt;</i> - source</code>

    -   <code>S4HANA for <i class="varname">&lt;ias-tenant-id&gt;</i> - target</code>

    -   <code>S4-<i class="varname">&lt;my312534&gt;</i>-source</code>

    -   <code>SAC-<i class="varname">&lt;my312534&gt;</i>-target</code>


2.  Review your *Identity Authentication* source and *SAP S/4HANA Cloud* target system configurations.

    The *Properties* holding connection and authentication details are preconfigured. Currently, both systems are configured to use basic authentication. If you want to use certificate-based authentication, follow the procedure described in step 3 of [Identity Authentication \(Source\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/e4e25f1fae094c2a89ad62159e1cd230.html) and [SAP S/4HANA Cloud \(Target\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/40940b8223334b528e4899b92d42ce96.html).

    You can now run a provisioning job to replicate your user data. However, before you do so, you may want to modify properties and transformations to further control how Identity Authentication data is replicated to SAP S/4HANA Cloud. For more information, search for properties prefixed with *<ias\>* and *<s4hana.cloud\>* in [List of Properties](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/d6f3577f30ec4af98e734b0126a60e37.html)

    > ### Note:  
    > Identity Provisioning cannot create and delete roles in SAP S/4HANA Cloud target system. It can only create, update and delete user assignments of a role. Therefore, roles must have been created in SAP S/4HANA Cloud system before you run a provisioning job. If you try to create or delete a role in SAP S/4HANA Cloud, Identity Provisioning will only add or remove the user assignments of that role, respectively.

3.  Run a provisioning job \(*Read* or *Resync*\). For more information, see; [Start and Stop Provisioning Jobs](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/531a2615b2d04eb8ba46a638b6d81cdc.html)

4.  Review your *SAP S/4HANA Cloud* source and *SAP Analytics Cloud* target system configurations.

    The *Properties* holding connection and authentication details are preconfigured. Currently, both systems are configured to use basic authentication. You can configure certificate-based authentication for SAP S/4HANA Cloud as described in step 3 of the following procedure: [SAP S/4HANA Cloud \(Source\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/d3f93a7870c341c0993cd733ed9e9b3a.html).

    You can now run a provisioning job to replicate your user data. However, before you do so, you may want to modify properties and transformations to further control how SAP S/4HANA Cloud data is replicated to SAP Analytics Cloud. For more information, search for properties prefixed with *<s4hana.cloud\>* and *<sac\>* in [List of Properties](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/d6f3577f30ec4af98e734b0126a60e37.html)

    Be aware of the following specifics related to groups in SAP Analytics Cloud:

    > ### Caution:  
    > When provisioning groups, note that they are mapped to teams in SAP Analytics Cloud. Those teams can then get role assignments in SAP Analytics Cloud.
    > 
    > If you run another provisioning job \(*Read* or *Resync*\), role assignments of SAP Analytics Cloud teams will be removed because of an update operation being executed. This behavior \(causing permission issues for users\) is expected, as SAP Analytics Cloud role assignments are not available as group parameters in some source systems, for example – Identity Authentication. To avoid this, you need to change the transformation of the SAP Analytics Cloud target system, as described in SAP Note[3027079](https://me.sap.com/notes/3027079)

    > ### Note:  
    > If you try to provision groups that already exist in SAP Analytics Cloud, your provisioning job may fail with: ***‘The group already exists on the target system and cannot be provisioned’*** error. For more information on when this could happen and how to proceed, see: [SAP Analytics Cloud \(Target\)](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/ea6a89de7a8242a497f42655bef9bef1.html)

5.  Run a provisioning job \(*Read* or *Resync*\).

    All provisioned users have the `PROFILE:sap.epm:Embedded_BI_Admin` embedded role assigned and can access SAP Analytics Cloud.

6.  \(Optional\) Configure additional source, target and proxy systems supported by the service for your scenarios as described in [Supported Systems](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/81ca0c1b51b449daac240a18ee0d3ab1.html).

    For more information on how to use the service for user provisioning in default and proxy mode, see the Identity Provisioning section in [Scenario Setup](../40-scenario-setup/scenario-setup-ae9137c.md).


