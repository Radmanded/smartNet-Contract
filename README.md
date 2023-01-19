# SmartNet-Contract

## Getting access to Cisco APIs 

<details>
<summary><h2>User onboarding process</h2></summary>

**Overview**

Cisco Services APIs are available only to Cisco Smart Net Total Care (SNTC) (https://www.cisco.com/c/m/en_us/customer-experience/support/smart-net-total-care.html) customers and their designated SNTC reseller Partners. Access is gated through a role-based process administered by the customer organization via the Cisco Services Access Management tool (https://cdceb.cloudapps.cisco.com/csam).

**Email Cisco API team for onboarding**

For Onboarding support questions please contact partner-integrations@cisco.com.

**API users accounts**

Specific registered Cisco.com user accounts (representing the application developer)(https://identity.cisco.com/ui/tenants/global/v1.0/enrollment-ui) are granted access to the Services APIs on behalf of a customer. These API users are then empowered to register unique application integration instances, generate API tokens, and start making API requests to retrieve a customer's service data.

An API user can be either:

**A customer user** - an internal developer who is a member of the customer's organization, previously onboarded to the customer's SNTC portal by the org's Delegated Administrator (DA).
  
**What's a delegated administrator?**

Note: This question is only applicable for Party-based APIs (example PSS API, EF API).
Cisco Service Access Management (CSAM) enables external partners to self-administer role-based user access to various Cisco Service programs. Self-administration is based upon the concept of delegated administration. Access is first granted, by Cisco, to one trusted person at the Customer or Partner Company, who then assumes responsibility for assigning access privileges to the rest of the users at their company.

You may already be using some other tool or process to manage CCO IDs for your users; however, CSAM is needed to perform these additional tasks before gaining access to the API Console:
•Associating user(s) to a party
•Assigning user(s) a role on the API Console

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

## Postman Resources
https://developer.cisco.com/docs/support-apis/#!cisco-support-apis-wadl-files/cisco-support-apis-wadl-files
  
## Contracts and Coverage
The Contracts API provides details about the contracts associated to the devices in a customer’s inventory. The Coverage API provides a list of all devices that are covered under the selected Cisco Contract number. If a device is not covered by a partner invoking the API, then information like contract number and other related API attributes are marked “confidential”.

## Features
The Contracts API provides the following features:

Supports RESTful interface, using a RAML definition file.
Supports JSON data format
Includes web services that return:
Contracts owned by customers or partners
Devices that are covered by a Cisco Service contract belonging to the customer or partner.
Devices in the inventory that are not covered by Cisco Service contract.  
  
## Contract Details
The contract details API returns details about specific contracts owned by customers or partners for devices in the customer’s inventory.
This API supports filtering, pagination, sorting and chunked transfer encoding. For more information, see General API Feature section for examples and features that allow you to optimize and manipulate the response.

### API URL
GET : https://apx.cisco.com/cs/api/v1/contracts/contract-details  
  
### Sample Request
https://apx.cisco.com/cs/api/v1/contracts/contract-details?customerId=1234

### Sample JSON Response
  
![image](https://user-images.githubusercontent.com/9085386/206316741-dc513793-a4fe-4f4e-bcc0-1b4d3cfabd22.png)
  
  
  
## Product Alerts
Product Alerts API provides information on the latest product alerts for a given partner/customer/inventory. The End of Life (EoL) service provides access to Cisco EoL product data. Customers and partners can request Cisco EoL product information for both hardware and software using a combination of input parameters. The Field Notice and Security Advisory API provides information on hardware and software issues involving Cisco products.

Features
The Cisco Product Information API provides the following features:

Supports RESTful interface, using a RAML definition file.
Supports JSON data format
Includes web services that return:
Field Notice information for a specific device or set of devicess.
Field Notice Bulletin details associated with a field notice.
Hardware End of Life details for a specific hardware device or set of devices.
Hardware Bulletins detail for the associated hardware device.
Security Vulnerability information including the Common Vulnerability and Exposure (CVE) identifiers and Common Vulnerability Scoring System (CVSS) for devices associated with customer ID.
Security Advisory bulletins detail for one or more security advisory IDs associated with the devices.
System Software End of Life details for a specific hardware device or set of devices.
System Software End of Life Bulletins detail for device(s) in the customer’s inventory

## Hardware End Of Life API
The Hardware End-of-Life API retrieves end of life details for a specific hardware device. All request parameters are optional other than “customerId”.

If "neInstanceId" is not provided in the request, the response will contain end of life information for all devices in the customer’s inventory.

This API supports filtering, pagination, sorting and chunked transfer encoding. For more information, see the General API Feature section for examples and features that allow you to optimize and manipulate the response.

###  API URL
GET : https://apx.cisco.com/cs/api/v1/product-alerts/hardware-eol
  
### Sample Request
https://apx.cisco.com/cs/api/v1/product-alerts/hardware-eol?customerId=1234

### Sample JSON Response  
  
![image](https://user-images.githubusercontent.com/9085386/206313991-0887a468-63d9-45dd-98ed-25c008dd28f7.png)
  

**More EOL APIs**
- https://developer.cisco.com/docs/service-apis/#!product-alerts/features
  
### EoX API (End of Life)

- https://developer.cisco.com/docs/support-apis/#!eox
  

## Security Advisory API

The PSIRT API returns security vulnerability information including the Common Vulnerability and Exposure (CVE) identifiers and Common Vulnerability Scoring System (CVSS) for devices associated with customer ID. All request parameters are optional other than “customerId”.

If device ID is not provided in the request, the response will contain security advisory information for all device IDs associated with the customer.

This API supports filtering, pagination, sorting and chunked transfer encoding. For more information, see the General API Feature section for examples and features that allow you to optimize and manipulate the response.

### API URL
GET : https://apx.cisco.com/cs/api/v1/product-alerts/security-advisories
  
### Sample Request
https://apx.cisco.com/cs/api/v1/product-alerts/security-advisories?customerId=1234

### Sample JSON Response
  
![image](https://user-images.githubusercontent.com/9085386/206314708-bc48747d-1109-400c-af2f-3d0781e573c7.png)

**More Security APIs**
- https://developer.cisco.com/docs/service-apis/#!product-alerts/features
  

## Software End Of Life
  
The Software End-of-Life API returns system software end of life details for a specific hardware device. All request parameters are optional other than “customerId”.

If "neInstanceId" is not provided in the request, the response will contain software end of life information for all devices in the inventory of the specified customer.

This API supports filtering, pagination, sorting and chunked transfer encoding. For more information, see the General API Feature section for examples and features that allow you to optimize and manipulate the response.

### API URL
GET : https://apx.cisco.com/cs/api/v1/product-alerts/software-eol  
  
### Sample Request
https://apx.cisco.com/cs/api/v1/product-alerts/software-eol?customerId=1234

### Sample JSON Response  
  
![image](https://user-images.githubusercontent.com/9085386/206315596-127555a2-7a58-44f2-8e55-e0a31f84c8f6.png)
  
  
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
  
- https://tools.ietf.org/html/rfc6749  

</details>

<details>
<summary><h2>Request API Access</h2></summary>

1. Go to Developer portal
https://anypoint.mulesoft.com/apiplatform/apx#/portals/

2. Search for API choosen from API Library

![image](https://user-images.githubusercontent.com/9085386/206319964-fe918ff7-b06f-42b7-a9fb-00cc43b580cb.png)

3. Choose API that matches your request
  
![image](https://user-images.githubusercontent.com/9085386/206320245-f5372102-f4ed-469c-9bc3-18dbf91a2708.png)
  
4. Request API Access
  
![image](https://user-images.githubusercontent.com/9085386/206320531-38e169fc-77c5-4cd7-a0c9-c99f1572f2f9.png)
  
<br>
  
![image](https://user-images.githubusercontent.com/9085386/206320951-6500058d-fca2-490d-94df-a23888f8facb.png)
  
<br>
  
![image](https://user-images.githubusercontent.com/9085386/206321110-92aed4b0-5d65-45b2-8f16-084a4297719c.png)
  
<br>

5. Verify API
  
<br>
  
![image](https://user-images.githubusercontent.com/9085386/206321420-c2c6a2e9-cb8e-4aba-93f8-02ff855485fa.png)
  
  
</details> 
  

<details>
<summary><h2>API Testing Environment</h2></summary>
  
How do I run and test the "HelloWorld" API on the Cisco env using OAuth 2.0?

The Hello API is a RESTful API built specifically to serve as the starting point for learning how to interact with APIs that are securely exposed through Cisco's API Console. APIs are protected using OAuth 2.0 standard. There are 3 steps involved to make a successful API call.

Step 1: Register an Application to use the HelloWorld API
Please refer to “How do I register an application for APIs?” (above)

Step 2: Generate an Access Token
Please refer to https://apiconsole.cisco.com/files/Token_Access.pdf
Access tokens can be generated using this OAuth 2.0 Spec guide (token developer guide) based on the grant type you choose. Every Access Token is valid for 60 min. After 60 min the application will have to request a new access token.

Step 3: Make an API request
Make a https GET request to https://api.cisco.com/hello and Pass the Access Token from Step 2 as part of the Request header; e.g., Authorization: Bearer
Functionally, the API concatenates the string "hello" to the single path parameter passed. If no path parameter is passed, it simply echoes back "Hello World".  
  
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

- https://apiconsole.cisco.com/Support  

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
