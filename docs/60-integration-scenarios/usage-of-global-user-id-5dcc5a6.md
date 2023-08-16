<!-- loio5dcc5a62e1004aa69bc4639646ddd8a8 -->

# Usage of Global User ID

The Global User ID identifier is immutable and unique across technology layers such as user interfaces, APIs, and security tokens, as well as across products and lines of business contributing to a business process in the Intelligent Enterprise.

We recommend using the Global User ID \(`userUUID`\) of SAP Cloud Identity Services - Identity Authentication as the federation identifier.



<a name="loio5dcc5a62e1004aa69bc4639646ddd8a8__section_hch_sy4_psb"/>

## Prerequisites

Identity Authentication and Identity Provisioning are configured in your landscape.



<a name="loio5dcc5a62e1004aa69bc4639646ddd8a8__section_ukk_2z4_psb"/>

## Usage

Identity Authentication is the home of the Global User ID. Identity Provisioning provisions the Global User ID to other systems in your landscape.

For provisioning users with a Global User ID to SAP S/4HANA, both Identity Provisioning and the on-premise SAP Identity Management can be used. Be aware of the following specifics:

-   Identity Provisioning requires that you first provision the users from Identity Authentication to the AS ABAP and then replicate them to SAP S/4HANA, as the Global User ID attribute mapping is handled in the default transformation of AS ABAP.

-   SAP Identity Management requires that you always run the ABAP or the Business Suite initial load job before the SAP S/4HANA initial load job. Thus, when you load the users from Identity Authentication and assign them the AS ABAP and the SAP S/4HANA account privileges in SAP Identity Management, they're provisioned with their Global User ID to SAP S/4HANA.


Applications can use the Global User ID attribute to correlate information. For example, SAP Task Center correlates the tasks of a given user from different systems. For more information, see [Integrating the Service with SAP Task Center](https://help.sap.com/viewer/6d6d63354d1242d185ab4830fc04feb1/Cloud/en-US/ab5e90ebb2914be9aa145494df048a32.html).

**Related Information**  


[SAP Task Center Documentation](https://help.sap.com/viewer/product/TASK_CENTER/Cloud/en-US)

