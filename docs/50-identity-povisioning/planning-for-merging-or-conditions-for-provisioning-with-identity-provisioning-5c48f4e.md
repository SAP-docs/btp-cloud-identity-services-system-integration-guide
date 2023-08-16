<!-- loio5c48f4e5d4714f4f909a339875fcb718 -->

# Planning for Merging or Conditions for Provisioning with Identity Provisioning

Exactly how to plan for merging or provisioning is an individual process for every organization. Unfortunately, we can't provide guidance on all the myriad of options available to you.

We can provide documentation about the transformation options offered by Identity Provisioning.

Yet, for the purposes of this integration guide, we can give you some relevant examples how to filter user data and how to avoid conflicts when merging it.



<a name="loio5c48f4e5d4714f4f909a339875fcb718__section_zbk_xzl_mrb"/>

## Example Configuration in the Source System

We assume that you want to provision some users from your SAP SuccessFactors, SAP S/4HANA Cloud and SAP Fieldglass systems to Identity Authentication based on specific criteria for each system. Normally, you do this by setting conditions in the default read transformations or by defining filtering properties in the source system.

-   **SAP S/4HANA Cloud** - Modify the default read transformation by adding a condition to filter users by specific business role. As a result, only the users assigned to the TEST\_ROLE business role will be provisioned to Identity Authentication.

    > ### Code Syntax:  
    > ```
    > {
    >     "user": {
    >         "condition": "($.user.role EMPTY false) && ($.user.role[?(@.roleName =='TEST_ROLE' )] != [])",
    >         "mappings": [
    > 
    > ```

-   **SAP Fieldglass** – Modify the default read transformation by adding a condition to filter users by specific division. As a result, only the users in that division \(0000\_TEST878\) will be provisioned to Identity Authentication.

    > ### Code Syntax:  
    > ```
    > {
    >     "user": {
    >         "condition": "$['resourceExtensions']['urn:ietf:params:scim:schemas:extension:enterprise:2.0:User']['division'] == '0000_TEST878'",
    >         "mappings": [
    > 
    > ```

-   **SAP SuccessFactors** - Define the `sf.user.filter` property on the *Properties* tab of the source system to filter users by specific department. As a result, only the users in that department \(Sales \(5000157\)\) will be provisioned to Identity Authentication.

    > ### Code Syntax:  
    > ```
    > sf.user.filter=department eq 'Sales (5000157)'
    > ```




<a name="loio5c48f4e5d4714f4f909a339875fcb718__section_iwf_zzl_mrb"/>

## Example Configuration in the Target System

When provisioning users from various source systems to a target system, it is a good practice to define the <code><i class="varname">&lt;system_prefix&gt;</i>.user.unique.attribute</code> property on the *Properties* tab of the target system. Thus, if Identity Provisioning tries to create a user that already exists in the target system, this property will help you resolve the conflict. It defines by which unique attribute\(s\) the existing user will be searched and resolved.

The default value is `userName`.

-   **Identity Authentication** - Add the `ias.user.unique.attribute` property and set its value to `userName`. Other possible values are `emails[0].value` or both `userName,emails[0].value` separated by comma.


> ### Example:  
> -   You have set the `ias.user.unique.attribute=userName`.
> 
> -   A user, named Joe Dow, exists in Microsoft Azure AD and SAP SuccessFactors with the following attributes.
> 
> 
>     <table>
>     <tr>
>     <th valign="top">
> 
>     Microsoft Azure AD
> 
> 
>     
>     </th>
>     <th valign="top">
> 
>     SAP SuccessFactors
> 
> 
>     
>     </th>
>     </tr>
>     <tr>
>     <td valign="top">
>     
>     *ObjectID*=`a203fa88-7897-4b07-81a1-675a9368a41e` 
> 
> 
>     
>     </td>
>     <td valign="top">
>     
>     *userID*=`Joe1` 
> 
> 
>     
>     </td>
>     </tr>
>     <tr>
>     <td valign="top">
>     
>     *userName*=`JoeD` 
> 
> 
>     
>     </td>
>     <td valign="top">
>     
>     *userName*=`JoeD` 
> 
> 
>     
>     </td>
>     </tr>
>     <tr>
>     <td valign="top">
>     
>     *firstName*=`Joe` 
> 
> 
>     
>     </td>
>     <td valign="top">
>     
>     *firstName*=`Joe` 
> 
> 
>     
>     </td>
>     </tr>
>     <tr>
>     <td valign="top">
>     
>     *lastName*=`Dow` 
> 
> 
>     
>     </td>
>     <td valign="top">
>     
>     *lastName*=`Dow` 
> 
> 
>     
>     </td>
>     </tr>
>     <tr>
>     <td valign="top">
>     
>     *email*=`joe@test.com` 
> 
> 
>     
>     </td>
>     <td valign="top">
>     
>     *email*=`joe@bestrun.com` 
> 
> 
>     
>     </td>
>     </tr>
>     </table>
>     
> 
> 1.  You run a provisioning job from Microsoft Azure AD to Identity Authentication. The user Joe Dow is created in Identity Authentication.
> 
> 2.  You run a provisioning job from SAP SuccessFactors to Identity Authentication.
> 
> 3.  Identity Provisioning finds out that a user with *userName* = `JoeD` already exists in Identity Authentication and resolves the conflict by overwriting the existing user \(from Microsoft Azure AD\) with the user data of the conflicting user \(from SAP SuccessFactors\).
> 
> 
> If a user with this *userName* is not found, the creation of the conflicting user fails. For more information, see: [List of Properties](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/d6f3577f30ec4af98e734b0126a60e37.html) → `ias.user.unique.attribute`
> 
> Administrators of Identity Provisioning tenants can control whether automatic conflict resolution is switched on or off in Identity Authentication target system by setting the `ias.user.automatic.conflict.resolution` property to true or false. For more information, see: [List of Properties](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/d6f3577f30ec4af98e734b0126a60e37.html) → `ias.user.automatic.conflict.resolution`

**Related Information**  


[Transformations](https://help.sap.com/viewer/f48e822d6d484fa5ade7dda78b64d9f5/Cloud/en-US/81f5204a5829429781d9ecc8b171f287.html)

