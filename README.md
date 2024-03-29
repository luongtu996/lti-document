### LTI 1.1

Please note that the API integration has been deprecated for LTI 1.1, and can only be used with LTI 1.3. Consider setting up with LTI 1.3 instead.

#### FROM ASSESSMENT

1. Obtain parameters from the registration page: `https://cohota-demo.heyhi.sg/adminv2/lti`
2. Select LTI 1.1

    By now, you should've obtained the following parameters from the registration page. 

    - Consumer Key
    - Secret Key
    - Config Url
![Config.Canvas.3](/images/v1.1/canvas3.png)

#### FROM LMS

1. Open your LMS and sign in with the admin account.
2. Click **Admin** from the left navigation pane.
3. Navigate to the account settings and select the **Apps** tab
![Config.Canvas.1](/images/v1.1/canvas1.png)
4. Click **+ App**. 
5. Enter the following information:
* **Configuration Type**: Select `By URL`
* **Name**: Enter `Assessment Response Tool`
* **Consumer Key**: Get from the app
* **Shared Secret**: Get from the app
* **Config URL**: Get from the app
![Config.Canvas.2](/images/v1.1/canvas2.png)
6. Click **Submit**.

You're all set. The Learn LTI tool is now configured on your Canvas LMS and your Educators will be able to use it to bring Assessment content to their courses.

### LTI 1.3

#### FROM ASSESSMENT

1. Obtain parameters from the registration page: `https://cohota-demo.heyhi.sg/adminv2/lti`
2. Configure an LTI tool on the LMS using the parameters from step 1.
3. Obtain parameters from the configured LTI tool.
4. Configure the Assessment application using the parameters from step 3.

By now, you should've obtained the following parameters from the registration page. 

- Redirect Url
- Login Url
- Config Url
![Config.Canvas.11](/images/config.canvas.11.png)

#### FROM LMS

1. Open your LMS and sign in with the admin account (Users who want to manage Developer Keys must have the **Developer Keys - manage** permission).
2. Click **Admin** from the left navigation pane, then click the name of the account.
3. Click **Developer Keys**.
4. Click **+Developer Key** and click **+LTI Key**.
5. Enter the following information:
* **Key Name**: give the tool a name of your choice. For example: "HeyHi Assessment".
* **Redirection URIs**: enter the "Redirect Url" from Assessment application’s lti page.
* **Method**: select **Enter URL**
* **JSON URL**: enter the "Config Url" from Assessment application’s lti page.
6. Click **Save**. The key should now appear and listed with the name you provided.
   ![Config.Canvas.1](/images/config.canvas.1.png)
7. Ensure that the newly added key is set to **Enabled**.
   ![Config.Canvas.1](/images/config.canvas.7.png)
8. Take note of the following parameters:
* **Client ID**: the number in the **Details** column, above the **Show Key** button
  ![Config.Canvas.2](/images/config.canvas.2.png)

At the account level, external tools must be installed in the External Apps page in Account Settings. LTI Advantage apps can be added via the Client ID option. Only the Client ID is required to be added.

1. Click **Settings** from the left navigation pane.
2. Click **Apps**.
3. Click **+App**.
4. Enter the following information:
* **Configuration Type**: select **By Client ID**
* **Client ID**: enter the "Client ID" from the LTI key registration.
  ![Config.Canvas.3](/images/config.canvas.3.png)
5. Click **Submit**.
6. If the Client ID is associated with an external tool, the tool name displays in the page. The page also confirms the tool should be installed.
   ![Config.Canvas.4](/images/config.canvas.4.png)
7. Click **Install**.
8. Continue to configure the Assessment application, by registering the parameters back in the Learn LTI application's registration page.

The following steps show how to register the parameters back in the Learn LTI application's registration page. If you are not the one who deployed the application, you need to provide these parameters to that person.

1. Open the tool registration page from your browser.
2. Enter the following information:
* **Client ID**: enter "Client ID" from the LTI key registration.
* **Keyset URL**: enter https://[tenant-name].instructure.com/api/lti/security/jwks
* **Authorization URL**: enter https://[tenant-name].instructure.com/api/lti/authorize_redirect
* **Access Token URL**: enter https://[tenant-name].instructure.com/login/oauth2/token
  NOTE: [tenant-name] is where your Canvas tenant name hosted by instructure. For example if the url of the LMS is https://canvas1.instructure.com, then the [tenant-name] is "canvas1". If you are using self-hosted Canvas, replace https://[tenant-name].instructure.com with your canvas URL.
* **Issuer**: enter your lms issuer, default is **https://canvas.instructure.com**
* **Deployment ID**: enter **Deployment ID** from the app
  ![Config.Canvas.5](/images/config.canvas.5.png)
5. Click **SAVE**.
   ![Config.Canvas.6](/images/config.canvas.6.png)
You're all set. The Learn LTI tool is now configured on your Canvas LMS and your Educators will be able to use it to bring Assessment content to their courses.
