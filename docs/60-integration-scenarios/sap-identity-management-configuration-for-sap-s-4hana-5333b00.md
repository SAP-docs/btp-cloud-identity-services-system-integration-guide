<!-- loio5333b00bf32c434d88caf56d313cc9b8 -->

# SAP Identity Management Configuration for SAP S/4HANA

Set up the systems for your provisioning scenario with SAP Identity Management and run the initial load jobs.



<a name="loio5333b00bf32c434d88caf56d313cc9b8__prereq_c3z_nqg_rrb"/>

## Prerequisites

-   You are running SAP Identity Management 8.0 SP08 or higher and SAP S/4HANA 2005 or higher.

-   You have imported the Identity Authentication, AS ABAP \(or SAP BusinessSuite\) and SAP S/4HANA connector packages in the SAP Identity Management 8.0 Developer Studio and you have configured the repositories for those systems.

    -   [Setting up an Identity Authentication System](https://help.sap.com/viewer/4773a9ae1296411a9d5c24873a8d418c/8.0/en-US/91ad2d3264f0475894e6be4da8756b92.html)

    -   [Setting Up an S/4HANA On-Premise System](https://help.sap.com/viewer/4773a9ae1296411a9d5c24873a8d418c/8.0/en-US/9c2d6d097a374744b5f907cd3ee345f5.html)

    -   [Setting Up an AS ABAP System](https://help.sap.com/viewer/4773a9ae1296411a9d5c24873a8d418c/8.0/en-US/ce3f5d445c824350b8a3a436ff7ede3f.html)


-   SAP S/4HANA integration with a human resource \(HR\) system, such as SAP HCM or SAP SuccessFactors, is inactive. In this case, IS\_HR\_INTEGRATION\_ACTIVE repository constant must be disabled in your SAP S/4HANA repository.

-   The following requirements related to the support for `userUUID` must be fulfilled:

    -   SAP Note [3047993](https://me.sap.com/notes/3047993) is applied on SAP Identity Management.

    -   SAP Note [3003462](https://me.sap.com/notes/3003462) is applied on SAP S/4HANA.

    -   The communication \(technical\) user defined on the JCO\_CLIENT\_USER repository constant \(ABAP or Business Suite repository\) has the authorization object S\_USER\_UID assigned through a role.



> ### Recommendation:  
> If you have an SAP S/4HANA system with existing business users, it is mandatory to run the ABAP or the Business Suite initial load job before the S/4HANA initial load. Otherwise, if SAP S/4HANA initial load is run first, this might cause an issue, where two separate person entries are created in SAP Identity Management - the business partner and its linked SU01 user, for one and the same business user in the SAP S/4HANA system. SAP Identity Management does not support cases where one business user is represented by two person entries. See: [Two Identities One Business User](https://help.sap.com/viewer/4773a9ae1296411a9d5c24873a8d418c/8.0/en-US/1030c9a172ab445d964716c40758b992.html)

<a name="task_sf1_sth_rrb"/>

<!-- task\_sf1\_sth\_rrb -->

## Load Users from Identity Authentication



<a name="task_sf1_sth_rrb__steps_ihz_xzl_mrb"/>

## Procedure

1.  In SAP Identity Management Administration User Interface \(UI\), run the initial load job for your Identity Authentication repository.

    Users with their `userUUID`s are loaded from Identity Authentication to SAP Identity Management.

2.  In SAP Identity Management UI, select the *Manage* tab and configure the following:

    1.  Select the *Assigned Roles and Privileges* tab and assign the AS ABAP and SAP S/4HANA account privileges to the users.

    2.  Select the *Settings* tab and provide values for the following attributes:

        *Business Partner Role Code* - This mandatory attribute holds the business partner role code. Enter `BUP003` which represents employee.

        *User Assignment - User ID* - This optional attribute holds the link of the business partner to the SU01 user. Enter the MSKEYVALUE of the users.

        If you leave the value empty, the business partner will be created with no link to the SU01 user, and the assignment will take place when the SU01 user is created.

        For more information about various cases when *User Assignment - User ID* is equal or different to the MSKEYVALUE, see: [Creating an S/4HANA Business User](https://help.sap.com/viewer/4773a9ae1296411a9d5c24873a8d418c/8.0/en-US/b5a59017bb744184a459c25ca831c924.html) 


3.  Choose *Save* to trigger the provisioning.

    The users are provisioned to SAP S/4HANA with their `userUUID`s. They are created as *User with Business Partner Assignment*.


<a name="task_nxm_5th_rrb"/>

<!-- task\_nxm\_5th\_rrb -->

## Create Users in SAP Identity Management



<a name="task_nxm_5th_rrb__steps_fgn_xth_rrb"/>

## Procedure

1.  In SAP Identity Management User Interface \(UI\), select the *Manage* tab and create a new user.

2.  Select the *Assigned Roles and Privileges* tab and assign the AS ABAP and SAP S/4HANA account privileges to the user.

3.  Select the *Settings* tab and configure the following attributes for the user:

    *Business Partner Role Code* - This mandatory attribute holds the business partner role code. Enter `BUP003` which represents employee.

    *User Assignment - User ID* - This optional attribute holds the link of the business partner to the SU01 user. Enter the MSKEYVALUE of the users.

    If you leave the value empty, the business partner will be created with no link to the SU01 user, and the assignment will take place when the SU01 user is created.

    For more information about various cases when *User Assignment - User ID* is equal or different to the MSKEYVALUE, see: [Creating an S/4HANA Business User](https://help.sap.com/viewer/4773a9ae1296411a9d5c24873a8d418c/8.0/en-US/b5a59017bb744184a459c25ca831c924.html) 

4.  Choose *Save*.

    This creates the user in SAP Identity Management and triggers the provisioning to SAP S/4HANA, where the user is created as a *User with Business Partner Assignment*.

5.  Assign the Identity Authentication account privilege to the same user.

    The user is provisioned to Identity Authentication. The userUUID attribute is generated and returned back to SAP Identity Management, where its value is stored in MX\_USER\_UUID. As this is an attribute that triggers the Modify process, SAP Identity Management updates the user in SAP S/4HANA with the `userUUID`.


**Related Information**  


[SAP S/4HANA Attributes](https://help.sap.com/viewer/b4c9306d80a3471aa0ae48511e725b43/8.0/en-US/7a5d1cf1aea44713b5ef1884a6ea8919.html)

