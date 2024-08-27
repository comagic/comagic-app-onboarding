# Salesforce Integration <br />

These instructions are for users who wish to set up an integration between CallGear and Salesforce CRM. Below is the functionality as well as the steps to set up the integration.

## Available Features <br />

<details>
<summary style="font-weight:bold;">Click to expand/collapse</summary> <br />

- **Automated Contact and Lead Creation**: Easily generate contact and lead records during incoming and outgoing calls with seamless automation.
- **Automated Call Routing**: Route calls to the appropriate manager (Сontact/Lead Owner) in Salesforce, ensuring efficient communication management.
- **Opportunity Creation**: Automatically create Opportunity after successful inbound and outbound or missed calls, facilitating a fast sales process.
- **Task Creation**: Automate the creation of tasks for successful inbound, outbound or missed calls, providing comprehensive customer support management.
- **Flexible Call Attachment Options**: Customize call attachments by linking call recordings to related tasks, opportunities, contacts or leads.
- **Customized Data Transfer**: Customize how data transfers from CallGear to specific Salesforce fields to improve data integrity.
- **Softphone Widget**: Initiate inbound and outbound calls directly within your CRM system with a convenient Softphone widget, enabling quick and efficient communication with customers and prospects.

</details>

<br />

---
## Integration Setup <br />
<details>
<summary style="font-weight:bold;">Salesforce Settings</summary> <br />

This section guides users on how to create a connected app within Salesforce. A connected app allows external applications to securely integrate with Salesforce using OAuth authentication.


- **Create a Connected App**:
  - Log in to your [Salesforce account](https://login.salesforce.com).
  - Go to advanced settings

![image](sf_auth_1.png)

- Navigate to Setup > Apps > App Manager.

![image](sf_auth_2.png)

- Click on 'New Connected App'.

![image](sf_auth_3.png)

- **Fill in the required details**:
  - Connected App Name: [Your App Name]
  - API Name: [Your_API_Name]
  - Contact Email: [Your Email Address]

![image](sf_auth_4.png)

- **Enable OAuth Settings: Must be checked**:
  - Callback URL:
    - https://uc-http-requester-dub-api.callgear.ae/oauth2/callback
    - https://uc-http-requester-lat-api.callgear.com/oauth2/callback

![image](sf_auth_5.png)

- Selected OAuth Scopes: Select required scopes based on your application needs.
- Also unchecking box “Require Proof Key for Code Exchange (PKCE) Extension for Supported Authorization Flows” and save.

![image](sf_auth_6.png)

- Save the changes.
- After saving, click on the “Initial Access Token” button.

![image](sf_auth_7.png)

</details>
<br />
<details>
<summary style="font-weight:bold;">Configure OAuth Settings</summary> <br />

- Once the Connected App is created, note down the 'Consumer Key' and 'Consumer Secret'. These will be used for authentication.
![image](sf_auth_8.png)
![image](sf_auth_9.png)

- Under the same Connected App settings, configure the OAuth policies, such as refresh token policy, token validity, etc., according to your requirements.

</details>
<br />
<details>
<summary style="font-weight:bold;">CallGear Credentials Settings</summary> <br />

#### Set Up Credentials <br />
  - Log in to your CallGear account using one of these links - https://go.callgear.com/ or https://go.callgear.ae/ 
  - Go to Marketplace and select Salesforce integration
  - Enter your Salesforce account URL and provide the necessary authentication keys from your Salesforce Connected App.

![image](sf_cred_settings.png)

</details>
<br />
<details>
<summary style="font-weight:bold;">Entity Creation Settings (Calls)</summary> <br />

- **Contact Creation**: 
  - Enable creation of Contact records for inbound and outbound calls.
  - Some opportunities and leads may not be found unless contact creation is enabled. Please enable contact creation to ensure proper automatic tracking and management of opportunities and tasks. <br />


- **Lead Creation**: 
  - Enable creation of Lead records for successful inbound, outbound and missed calls.
  - Specify the status with which the lead will be created.

![image](sf_lead_status.gif)

<br />

- **Opportunity Creation**: 
  - Enable creation of Opportunity records for successful inbound, outbound and missed calls.
  - Specify the stage with which the lead will be created.
  - Specify the days until close (close date field of opportunity). Example: if call was made 01.01 and days until close = 14, then close date of opportunity on this call will be 01.15.
  - Opportunity will be created if there are no opportunities in open stage.

![image](sf_opportunity_stage.gif)

<br />

- **Task (Call log) Creation**: 
  - Enable Task creation for successful inbound, outbound and missed calls.
  - Specify the status and priority with which the task will be created.
  - Task will be created on every call.
  - To avoid creating tasks for missed outbound calls, the option can be disabled using the checkbox.

![image](sf_task.gif)

<br />

- **Attachment Creation**: 
  - Enable Attachment creation for successful inbound and outbound calls.
  - If turned on, call record will be loaded into Salesforce as Attachment and connected to chosen entity.

![image](sf_attachments.png)

<br />

- **Call Details Mapping**:
  - Configure the transfer of call information from CallGear to Salesforce:
    - Choose an object type: Contacts, Leads, Opportunities, Tasks.
    - Select the information you want to transfer from CallGear.
    - Select the field in the Salesforce object to which this information will be transferred.

![image](sf_mapping.gif)

</details>
<br />

<details>
<summary style="font-weight:bold;">Entity Creation Settings (Chats)</summary> <br />

- **Most of the settings for creating entities in chats are similar to those in calls.**
<br /><br />

- The main differences are:
  - Entities will be created once for each chat opening (a message from a client or an employee wrote first) regardless of the number of messages before closing this chat.
  <br /><br />
  - When a chat is opened by an incoming message from a client, an employee has not yet been assigned to it. Consequently, there is no option to attach an owner when creating an entities. The owner would be defaulted on creation by internal Salesforce settings. Owner could be assigned after the employee replies if the setting is enabled in the integration. 
  <br /><br />
  - Sometimes the phone of the visitor could be hided. In this case only Task could be created if the related option is enabled in the integration settings. If the option is disabled, nothing will be created in such cases.

</details>
<br />

<details>
<summary style="font-weight:bold;">CallGear Softphone Widget</summary> <br />

1.  **Installation**:
    - Use the <a href="https://chromewebstore.google.com/detail/callgear/gmepbeelpjhhlnkccmclgijnnleadijl" style="color: blue; text-decoration: none;">provided link</a> to download and install the widget.
2.  **Authorization**:
    - Authenticate using your CallGear account credentials.
    - Log in to the installed widget under the same account.
3.  **Functionality Check**:
    - Enable the "Show softphone" option.
    - Make sure that the widget icon is displayed.

</details>
<br />

---

## Support <br />


If you have any problems or additional questions, please contact <a href="mailto:support@callgear.com" style="color: blue; text-decoration: none;">CallGear Support</a> for assistance.