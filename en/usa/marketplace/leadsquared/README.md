# Leadsquared Integration

## Available features

<details>
<summary>Click to expand/collapse</summary>

- **Automated Lead Creation**: Automatically create leads after successful inbound, outbound, or missed calls.
- **Automated Call Routing**: Route calls to the appropriate manager (customer owner) in Leadsquared, ensuring efficient communication management.
- **Click-to-Call Widget**: Initiate inbound and outbound calls directly within your Leadsquared system with a convenient Softphone widget, enabling quick and efficient communication with customers and prospects.

</details>

## Integration Setup

<details>
<summary>Initial Setup Steps & CallGear Softphone Widget</summary>

### Initial Steps

1. **Turn on integration**:
    - Go to the Integration section (left sidebar).
    - Click on Leadsquared in the list of integrations and proceed to its configuration.
2. **Authorization**:
    - Add Leadsquared Credentials Name.
    - Go to Leadsquared Settings - API and Webhooks. <br>![img.png](img.png)
    - Copy API host, API Key and Secret Key. <br>![img_1.png](img_1.png)
    - Paste this data into the credentials form.<br> ![img_2.png](img_2.png)
    - Click add and that’s it.

### CallGear Softphone Widget <br />

1.  **Installation**:
    - Use the <a href="https://chromewebstore.google.com/detail/callgear/gmepbeelpjhhlnkccmclgijnnleadijl" style="color: blue; text-decoration: underline;">provided link</a> to download and install the widget.
2.  **Authorization**:
    - Authenticate using your CallGear account credentials.
    - Log in to the installed widget under the same account.
3.  **Functionality Check**:
    - Enable the "Show softphone" option within <a href="https://leadsquared.com/" style="color: blue; text-decoration: underline;">Leadsquared</a>.
    - Make sure that the widget icon is displayed.

</details>

<details>
<summary>Integration with LeadSquared Mobile Connector</summary>


 **Integrate with LeadSquared Mobile Connector**:
   - Install the connector from Marketplace <br> ![img_3.png](img_3.png)
   - Use the modified webhook URL (with the appended endpoint path) in your LeadSquared Mobile Connector configuration.
   - After installation, click on the gear icon and proceed to configure.
   - Select the preferable setting. In our case, we use Only cloud calling with Phone as User field with Virtual Number <br> ![img_4.png](img_4.png)
   -  **Click2Call**:
       - Click on the `Click to Call Set-up` button and paste the webhook URL you get in the `Webhook URL` and append the endpoint path to it. Set method to `POST` and paste the body template![img_5.png](img_5.png)
       - ```json
             {"agent_email": "@{User:EmailAddress}","customer_number": "@{Lead:Phone}"}
         ```
       - Click `Go to Test API`, then enter some data from your Leadsquared account and click `Test And Map Response`. If everything is correct, you will see the response
      ![img_6.png](img_6.png)
       - Map the response and click `Save` <br>![img_7.png](img_7.png)
   - **Pop-up**: 
       - Click on the `Incoming Agent Pop-up` button and paste the webhook URL you get in the `Webhook URL` and append the endpoint path to it. Set method to `POST` and paste the body template![img_8.png](img_8.png)
       - ```json
             {"agent_phone": "@{User:PhoneMain}"}
         ```
       - Click `Go to Test API`, then press `Test And Map Response`. If everything is correct, you will see the response <br>![img_9.png](img_9.png)
       - Map the response and click `Save` <br>![img_10.png](img_10.png)
   - **DID**:
       - Click on the `DID` button and paste the webhook URL you get in the `Webhook URL` and append the endpoint path to it. Set method to `GET` <br>![img_11.png](img_11.png)
       - Click `Go to Test API`, then press `Test And Map Response`.
       - Map the response and click `Save`  <br>![img_12.png](img_12.png)
   - That’s it. Now you can use the CallGear Softphone Widget with LeadSquared Mobile Connector.

</details>

<details>
<summary>Syncing Details</summary>

### Sync Contacts
Synchronizes contacts from Leadsquared to CallGear by parsing new leads. If the lead has a meaningful name (not just a phone number) and the phone number is not already in the contact book, the contact will be synced.

### Sync Users
Synchronizes users from Leadsquared to CallGear. A user will be synced if there is no user with the same email in CallGear.

</details>