# SmartNet-Contract

Creating a chatbot with the botkit template. Please ensure that you have all the Pre-reqs installed on your device. 

# Pre-requsites

-  CCOID 
-  


<details>
<summary><h2>User onboarding process</h2></summary>

**Overview**

Cisco Services APIs are available only to Cisco Smart Net Total Care (SNTC) (https://www.cisco.com/c/m/en_us/customer-experience/support/smart-net-total-care.html) customers and their designated SNTC reseller Partners. Access is gated through a role-based process administered by the customer organization via the Cisco Services Access Management tool (https://cdceb.cloudapps.cisco.com/csam).

**API users accounts**

Specific registered Cisco.com user accounts (representing the application developer)(https://identity.cisco.com/ui/tenants/global/v1.0/enrollment-ui) are granted access to the Services APIs on behalf of a customer. These API users are then empowered to register unique application integration instances, generate API tokens, and start making API requests to retrieve a customer's service data.

An API user can be either:

**A customer user** - an internal developer who is a member of the customer's organization, previously onboarded to the customer's SNTC portal by the org's Delegated Administrator (DA).

**A partner user** - an external/non-customer developer, whose Cisco.com ID is a member of a SNTC Cisco reseller partner organization. The partner organization must have at least one valid SNTC contract with the delegating customer's organization.

**Granting API access**

The customer SNTC Delagated Administrator grants API access to an API user via the Cisco Services Access Management Tool.

The steps vary slightly for customer vs. partner users:

Granting API access for customer users - https://www.cisco.com/c/dam/en/us/support/docs/services/sntc/Guide-to-Assigning-Customer-API-Roles.pdf

Granting API access for partners users - https://www.cisco.com/c/dam/en/us/support/docs/services/sntc/Guide-to-Assigning-API-Role.pdf

Once the onboarding process is complete, the API user can access the Cisco API Developer Portal to register an application with one-or-more of the Services APIs.

- https://developer.cisco.com/docs/service-apis/#!user-onboarding-process/user-onboarding-process

**Guide**

- https://www.cisco.com/c/en/us/support/docs/services/sntc/onboarding_guide.html

</details>


<details>
<summary><h2>API Library</h2></summary>

**EoX API (End of Life)**

- https://developer.cisco.com/docs/support-apis/#!eox


</details>

<details>
<summary><h2>Application Registration</h2></summary>

Registering an application with the Cisco API Developer Portal generates all the details needed to successfully complete the authentication sequence.

Support APIs applications require an API "access token" in order to authenticate each individual API request. To generate such an access token (typically performed upon startup, or just prior to accessing the API), the application performs an OAuth2 client credentials grant flow. Registering an application with the Cisco API Console generates all the details needed to successfully complete the authentication sequence.

Regarding application registrations:

API users can register multiple applications.

A single application registration can be configured to access one-or-more of the individual Support APIs.

Each registration represents the identity/role/access/permissions of the API user that created it, with regards to any customer data.

Registering an application generates a set of credentials - the Client ID and Client Secret - which are submitted in the OAuth2 authentication request.

These credentials are secrets unique to the registered application, and must be carefully protected, just as a username/password would be. They do not expire, however they can be revoked/regenerated in the API Console by the API user if they are ever compromised (this will likely require re-populating the ID/secret into the runtime configuration of any apps using the old set of secrets.)

- https://developer.cisco.com/docs/support-apis/#!application-registration/application-registration

## Oauth2 Instructions

- https://apiconsole.cisco.com/docs/read/overview/Oauth_20_Topics

</details>


<details>
<summary><h2>Guide to Enabling Partner Access to Service APIs</h2></summary>
<br>
- https://www.cisco.com/c/dam/en/us/support/docs/services/sntc/Guide-to-Assigning-Customer-API-Roles.pdf

</details>

<details>
<summary><h2>Cisco Smart Net Total Care Portal Administration and Management</h2></summary>

## Manage Portal Access

A customer administrator can grant or remove access to specific types of information, capabilities, and inventories and segments on a user-by-user basis. Complete these steps in order to control these rights:

Log into the Smart Net Total Care portal.
From the Admin dashboard, click in order to maximize the Users pane.
Choose the user from the list.
Select Actions > Manage Access.
Check or uncheck the items that are listed in order to control access. These are the available options:
Information:
Product alerts
Device configuration
LOA privilege information (only available for CBR Administrator or CBR User)
Service API Access (only available for CBR Administrator)
Capabilities:
Service Coverage Management
Alert Management
Update Device Site Information
You can also control access to individual inventory or segment installed base data.
Click Confirm in order to save your selections. The user should experience the new permissions upon their next login to the portal.

## Request Partner Delegated Administrator (For Partners Only)
Partners selling Smart Net Total Care who access the portal to support their customers or who use SNTC for their own Partner company need to ensure the Partner company has a DA assigned. This allows them to manage Partner users and be granted access to their customers' data in the SNTC portal in a Cisco Branded Reseller (CBR) role (either as a CBR Administrator or CBR User).

Complete these steps in order to assign a DA for your partner company:

Login to the Partner Self-Service tool with your CCO ID.
Click View Profile to see a list of administrators for your partner company
Select one administrator to nominate as the Delegated Admin.
Send an email to sntc-support@cisco.com to nominate your partner admin as the Delegated Admin.
(If the partner is in the China region send the email to chinese-tac@cisco.com)
Subject line: Partner Delegated Administrator Setup Request
Content: Provide the CCO ID, company name, and email address of your nominee and the SNTC contract # of the customer for which you will have a CBR role in the portal
Cisco will setup the Delegated Admin for your partner company and send an email notifying that they have been nominated to become the DA. The email provides a link to accept the Terms and Conditions which they must click to Accept.

The DA can then follow the steps to Add New Users to the Portal and Assign Roles including nominate another user from their partner company as a DA. Once users are associated with the partner company, customers can then follow steps to Add Partners to the Portal and Assign Roles. A customer can also grant their Partner CBR Admin the right to add other partner users to the portal on their own. Follow the steps to give CBR Administrator Rights to Add Partner Users.

</details>


<details>
<summary><h2>Videos</h2></summary>

- https://www.cisco.com/c/en/us/support/services/sntc-portal/video-resources.html?videoId=5384974006001

</details>


<details>
<summary><h2>Support</h2></summary>

- For Onboarding support questions please contact partner-integrations@cisco.com.

- For Production support questions please follow the instructions at https://www.cisco.com/E-Learning/gbo-ccw/cdc_bulk/Cisco_Commerce_Misc/B2B_Support.pdf to open a case.

> Note: Partner Onboarding Environment (POE) is the recommended environment to test your solution. DO NOT TEST in CISCO’s PRODUCTION ENVIRONMENT. A subset of your production data has been provisioned in this test environment for your convenience. The data subset replication takes place after every Cisco quarterly release and hence available subset is as of Cisco release date.

<details>
<summary><h2>Blogs</h2></summary>

- https://community.cisco.com/t5/pss-documentation-library/request-access-to-the-pss-apis/ta-p/4094595

</details>

<details>
<summary><h2>Extras</h2></summary>

## Find a Contract Number and Add Access to Your Contract Number

- https://www.cisco.com/c/en/us/support/docs/security/web-security-appliance/118223-qanda-csa-00.html

/details>
