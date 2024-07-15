# Salesforce Custom Object <br />

These instructions are for users who wish to set up an integration between CallGear and Salesforce CRM. Below is the functionality as well as the steps to set up the integration.


<br />

---
## Integration Setup <br />
This integration is an add-on to the main Salesforce integration that allows you to work with Custom Objects. If you want to set up attachments for the main entities, please do so in the main Salesforce integration.

If you have already connected the main Salesforce integration, you may use the same credentials and skip the first 3 sections — go right to the Entity Creation Settings.
<details>
<summary style="font-weight:bold;">Salesforce Settings</summary> <br />

This section guides users on how to create a connected app within Salesforce. A connected app allows external applications to securely integrate with Salesforce using OAuth authentication.


- **Create a Connected App**:
  - Log in to your [Salesforce account](https://login.salesforce.com).
  - Go to advanced settings

![image](../SalesForce/sf_auth_1.png)

- Navigate to Setup > Apps > App Manager.

![image](../SalesForce/sf_auth_2.png)

- Click on 'New Connected App'.

![image](../SalesForce/sf_auth_3.png)

- **Fill in the required details**:
  - Connected App Name: [Your App Name]
  - API Name: [Your_API_Name]
  - Contact Email: [Your Email Address]

![image](../SalesForce/sf_auth_4.png)

- **Enable OAuth Settings: Must be checked**:
  - Callback URL:
    - https://uc-http-requester-dub-api.callgear.ae/oauth2/callback
    - https://uc-http-requester-lat-api.callgear.com/oauth2/callback

![image](../SalesForce/sf_auth_5.png)

- Selected OAuth Scopes: Select required scopes based on your application needs.
- Also unchecking box “Require Proof Key for Code Exchange (PKCE) Extension for Supported Authorization Flows” and save.

![image](../SalesForce/sf_auth_6.png)

- Save the changes.
- After saving, click on the “Initial Access Token” button.

![image](../SalesForce/sf_auth_7.png)

</details>
<br />
<details>
<summary style="font-weight:bold;">Configure OAuth Settings</summary> <br />

- Once the Connected App is created, note down the 'Consumer Key' and 'Consumer Secret'. These will be used for authentication.
![image](../SalesForce/sf_auth_8.png)
![image](../SalesForce/sf_auth_9.png)

- Under the same Connected App settings, configure the OAuth policies, such as refresh token policy, token validity, etc., according to your requirements.

</details>
<br />
<details>
<summary style="font-weight:bold;">CallGear Credentials Settings</summary> <br />

#### Set Up Credentials <br />
  - Log in to your CallGear account using one of these links - https://go.callgear.com/ or https://go.callgear.ae/ 
  - Go to Marketplace and select Salesforce integration
  - Enter your Salesforce account URL and provide the necessary authentication keys from your Salesforce Connected App.

![image](../SalesForce/sf_cred_settings.png)

</details>
<br />
<details>
<summary style="font-weight:bold;">Entity Creation Settings</summary> <br />

In Salesforce, a custom object is a user-defined database table that allows you to store information unique to your organization. Custom objects are similar to standard objects (such as Accounts, Contacts, and Opportunities) provided by Salesforce, but they are created to cater to specific business needs that standard objects do not address.

- You can add up to 25 different Salesforce objects. 

![image](sf_cobj1.png)

- Select the object type you want to create.
  - **! Every field in one object should have the same object type.**

![image](sf_cobj2.png)

- Select CallGear and Salesforce fields.
  - Select the information you want to transfer from CallGear.
  - Select the field in the Salesforce object to which this information will be transferred.
  - Salesforce fields marked with ** are required. Without setting these fields, the object will not be created.
  - Salesforce fields marked with * if not set, the value will be defaulted on creation by Salesforce settings.
  - After the call finishes, the object will be created in Salesforce.

![image](sf_cobj3.gif)

- Instead of selecting CallGear field, you can write your own text.

![image](sf_cobj4.png)

- You can concatenate multiple CallGear fields with each other or with manual text in one Salesforce field.

![image](sf_cobj5.png)

- Select the type of call at which the object will be created

![image](sf_cobj6.png)

- Create duplicates switch.
  - If turned on, the object will be created every call.
  - If turned off, system will try to find the object in Salesforce before creation, if object is not found, it will be created.
  - **If one or more chosen fields is not searchable, the object will not be found and will be created.**

![image](sf_cobj_7.png)

- CallGear call parameters description.
  - [Link](https://docs.google.com/spreadsheets/d/19sJGpZEH-tfLBPMhW2xjKrmfK4L8O8T8kpEbet8Ou_Q/edit?usp=sharing)

</details>

---

## Support <br />


If you have any problems or additional questions, please contact <a href="mailto:support@callgear.com" style="color: blue; text-decoration: none;">CallGear Support</a> for assistance.