# SalesForce Custom Object <br />

These instructions are for users who wish to set up an integration between CallGear and SalesForce CRM. Below is the functionality as well as the steps to set up the integration.


<br />

---
## Integration Setup <br />
If you have already connected main Salesforce integration, you can choose the same credentials and skip this section.
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
  - Go to Marketplace and select SalesForce integration
  - Enter your Salesforce account URL and provide the necessary authentication keys from your Salesforce Connected App.

![image](../SalesForce/sf_cred_settings.png)

</details>
<br />
<details>
<summary style="font-weight:bold;">Entity Creation Settings</summary> <br />

- You can add up to 25 different Salesforce objects. 

![image](sf_cobj1.png)

- Select the object type you want to create.
  - Every field in one object should have the same object type.

![image](sf_cobj2.png)

- Select CallGear and SalesForce fields.
  - Select the information you want to transfer from CallGear.
  - Select the field in the SalesForce object to which this information will be transferred.
  - SalesForce fields marked with ** are required. Without setting these fields, the object will not be created.
  - SalesForce fields marked with * if not set, the value will be defaulted on creation by SalesForce settings.
  - After the call finishes, the object will be created in Salesforce.

![image](sf_cobj3.gif)

- Instead of selecting CallGear field, you can write your own text.

![image](sf_cobj4.png)

- You can concatenate multiple CallGear fields with each other or with manual text in one SalesForce field.

![image](sf_cobj5.png)

- Select the type of call at which the object will be created

![image](sf_cobj6.png)

</details>

---

## Support <br />


If you have any problems or additional questions, please contact <a href="mailto:support@callgear.com" style="color: blue; text-decoration: none;">CallGear Support</a> for assistance.