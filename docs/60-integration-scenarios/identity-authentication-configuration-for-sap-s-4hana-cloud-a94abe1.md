<!-- loioa94abe163a7f45809d09d4a09bfddc70 -->

# Identity Authentication Configuration for SAP S/4HANA Cloud



<a name="loioa94abe163a7f45809d09d4a09bfddc70__prereq_ttc_glm_rrb"/>

## Prerequisites

You’ve completed the steps for the initial admin user. For more information, see [Process Overview](https://help.sap.com/viewer/DRAFT/b249d650b15e4b3d9fc2077ee921abd0/2202.500/en-US/96fe8c72bac74f7a9433e5de17740c4e.html) .



## Context

Every SAP S/4HANA system comes with an SAP Cloud Identity Services - Identity Authentication tenant. You’ve received a provisioning e-mail with initial access information for Identity Authentication.

For the configuration in the administration console for Identity Authentication, you must upload your users in the tenant:



<a name="loioa94abe163a7f45809d09d4a09bfddc70__steps_unk_ylm_rrb"/>

## Procedure

1.  Log on to the tenant's administration console for Identity Authentication using the access information in the provisioning e-⁠mail.

2.  Choose the *Import Users* tile.

3.  Select your SAP S/4HANA system under Applications.

4.  Choose the *Browse...* button and specify the location of the CSV file that includes your administrator business user.

5.  Choose the *Import* button, to update the user data in Identity Authentication.

6.  Choose *Send E-Mails* \> *Send*.


**Related Information**  


[User Onboarding for SAP S/4HANA Cloud with SAP Central Business Configuration in the 3-system landscape](https://help.sap.com/viewer/DRAFT/b249d650b15e4b3d9fc2077ee921abd0/2202.500/en-US/fe1022c05f4a4a9f871395f19883faac.html)

[SAP Cloud Identity Services REST APIs](https://api.sap.com/package/SCPIdentityServices/rest)

