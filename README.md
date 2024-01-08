# Configure the tool

The following guide shows the steps to configure several popular LMS to work with the Assessment application. If your LMS is not listed here, consult your LMS vendor on how to configure LTI application. Regardless of the LMS, the typical workflow should remain the same:

1. Obtain parameters from the deployed Assessment application’s registration page
2. Configure an LTI tool on the LMS using the parameters from step 1.
3. Obtain parameters from the configured LTI tool.
4. Configure the Assessment application using the parameters from step 3.

By now, you should've obtained the following parameters from the Assessment application’s registration page. 

- Redirect Url
- Login Url
- Config Url

## Canvas LMS

The following steps show how to configure an LTI tool on a Canvas LMS.

### LTI 1.1

At this time, we do not support LTI 1.1 with Canvas LMS.

### LTI 1.3

The LTI 1.3 and LTI Advantage platform requires a tool to be initially configured in the Developer Keys page, followed by being added to an account or course. First, configure the tool in the Developer Keys page.

1. Open your LMS and sign in with the admin account (Users who want to manage Developer Keys must have the **Developer Keys - manage** permission).
2. Click **Admin** from the left navigation pane, then click the name of the account.
3. Click **Developer Keys**.
4. Click **+Developer Key** and click **+LTI Key**.
5. Enter the following information:
* **Key Name**: give the tool a name of your choice. For example: "HeyHi Assessment".
* **Redirection URIs**: enter the "Redirect Url" from Assessment application’s registration page.
* **Method**: select **Enter URL**
6. Click **Save**. The key should now appear and listed with the name you provided.
   ![Config.Canvas.1](/images/config.canvas.1.png)
7. Ensure that the newly added key is set to **Enabled**.
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
* **Issuer**: enter **https://canvas.instructure.com** (this should always be canvas.infrastructure.com not matter your tenant url)
* **Deployment ID**: enter **Deployment ID** from the app
  ![Config.Canvas.5](/images/config.canvas.5.png)
5. Click **SAVE**.
   ![Config.Canvas.6](/images/config.canvas.6.png)
You're all set. The Learn LTI tool is now configured on your Canvas LMS and your Educators will be able to use it to bring Microsoft Learn content to their courses. Follow the [educator guide](./USER_GUIDE.md) to create assignments that use the Learn LTI tool.

## Blackboard Learn LMS

The following steps show how to configure an LTI tool on a Blackboard Learn LMS.

### LTI 1.1

At this time, we do not support LTI 1.1 with Blackboard Learn LMS.

### LTI 1.3

Before the LTI Tool can be added to specific Blackboard Learn LMS Tenant, it needs to be registered as an app in Blackboard Dev Portal.

1. Open your browser and go to https://developer.blackboard.com/.
2. Click **Register** to Register and Manage Your Applications.
3. Accept the **Terms & Condition** and click **Agree & Continue**.
4. Create a New Account to register your application. If you already have an account, sign in with one.
5. Click the **+** icon to register a new application.
6. Enter the following information:
* **Application Name**: give the tool a name of your choice. For example: "Microsoft Learn".
* **Description**: give the tool a description.
* **Domain**: enter “Domain URL” from the Assessment application’s registration page.
* **My Integration supports LTI 1-3**: Enabled.
  ![Config.Blackboard.1](/images/Config.Blackboard.1.png)
* **Login Initiation URL**: enter "Login URL" from the Assessment application’s registration page.
* **Tool Redirect URL(s)**: enter the "Launch URL" from Assessment application’s registration page.
* **Tool JWKS URL**: enter "Public JWK Set URL" from the Assessment application’s registration page.
  ![Config.Blackboard.2](/images/Config.Blackboard.2.png)
7. Click **Register application and generate API Key**.
8. ⚠️ The secret is only shown once. Make note of the application key and secret and store them in a safe and secure location.
9. Take note of the following parameters:
* **Application ID**: the string under the **Application ID** column.

Now you are ready to add the app as an LTI Provider in your Blackboard Learn LMS.

1. Open your LMS and sign in with the admin account.
2. Click **Admin** from the left navigation pane to open the Administrator Panel.
3. Click **LTI Tool Providers** under **Integrations**.
4. Click **Register LTI 1.3/Advantage Tool**.
5. Enter the following information:
* **Client ID**: enter the "Application ID" from the LTI key registration.
6. Click **Submit**.
   ![Config.Blackboard.3](/images/Config.Blackboard.3.png)
7. Ensure that **Tool Status** is set to **Approved**.
8. Under Institution Policies:
* Ensure that all **User Fields to Send** are selected.
* **Allow grade service access**: Yes
* **Allow Membership Service Access**: Yes
9. Click **Submit**.
   ![Config.Blackboard.4](/images/Config.Blackboard.4.png)
10. Select the newly registered tool and click **Manage Placements**.
11. Click **Create Placements**.
12. Enter the following information:
* **Label**: give the placement a label. For example: "Microsoft Learn".
* **Handle**: give the placement a handle.
* **Availability**: Yes
* **Type**: Course content tool
* **Allows grading**: Selected
* **Launch in New Window**: Selected
* **Target Link URI**: enter the "Launch URL" from Assessment application’s registration page.
13. Click **Submit**.
14. Continue to configure the Assessment application, by registering the parameters back in the Learn LTI application's registration page.

The following steps show how to register the parameters back in the Learn LTI application's registration page. If you are not the one who deployed the application, you need to provide these parameters to that person.

1. Open the tool registration page from your browser.
2. Enter the following information:
* **Display name**: give the tool a name of your choice.
* **Issuer**: enter **https://blackboard.com**
* **JWK Set URL**: enter https://developer.blackboard.com/api/v1/management/applications/[application-id]/jwks.json, where [application-id] is the "Application ID" from the LTI key registration.
* **Access Token URL**: enter https://developer.blackboard.com/api/v1/gateway/oauth2/jwttoken
* **Authorization URL**: enter https://developer.blackboard.com/api/v1/gateway/oidcauth
* **Client ID**: enter "Application ID" from the LTI key registration.
* **Audience**: This can be left blank
3. Optionally, you can add your Institution name and logo on the registration page.
4. Click **SAVE REGISTRATION**..

You're all set. The Learn LTI tool is now configured on your Blackboard Learn LMS and your Educators will be able to use it to bring Microsoft Learn content to their courses. Follow the [educator guide](./USER_GUIDE.md) to create assignments that use the Learn LTI tool.

## Brightspace D2L

The following steps show how to configure the MS Learn LTI Tool on a Brightspace LMS.

### LTI 1.1

At this time, we do not support LTI 1.1 with Brightspace LMS.

### LTI 1.3

Before the Links to MSLearn LTI Links can be added to courses, It must be registered and deployed into the tenant. LTI 1.3 in Brightspace is known as LTI Advantage.

1. Open your browser and go to your Brightspace environment as a superadmin.
2. Click the gear at the top right corner and select **External Learning Tools**.
3. Select the **LTI Advantage** Tab.
4. Click the **New Deployment** button.
5. Click the *?* icon next to the Select Registered Tool Button. and in the resulting window Click the **Register** link.
   ![Config.Brightspace.1](/images/Config.Brightspace.1.png)
6. Click **Register Tool** on the resulting page.
7. In the next screen. Select **Standard**.
8. Enter the following information:
* **Name**: give the tool a name of your choice. For example: "Microsoft Learn".
* **Description**: give the tool a description. Optional.
* **Domain**: enter “Domain URL” from the Assessment application’s registration page. Note: Put HTTPS:// in front of the domain.
* **Redirect URLs**: enter “Launch URL” from the Assessment application’s registration page.
* **OpenID Connect Login URL**: enter “Login URL” from the Assessment application’s registration page.
* **Redirect URLs**: enter “Launch URL” from the Assessment application’s registration page.
* **Target Link URI**: enter “Launch URL” from the Assessment application’s registration page.
* **Keyset URL**: enter “Public JWK Set URL” from the Assessment application’s registration page.
* **Extensions**: Ensure at least Name and Role Provisioning Services is checked.
* **Roles-> Send Institution Role**: Unchecked.
  ![Config.Brightspace.2](/images/Config.Brightspace.2.png)
9. Once Registered, It will give you a set of Brightspace Registration Details. This Includes:
   Client Id, Brightspace Keyset URL, Brightspace OAuth2 Access Token URL, OpenID Connect Authentication Endpoint, Brightspace OAuth2 Audience, and Issuer.
   You will need this information to register the platform back to the Learn LTI Application's registration page.
10. Follow Steps 2-4 to return to the **New Deployment** page.
11. Select the Newly Registered Tool
* **Name**: give the tool Deployment a name of your choice. For example: "Microsoft Learn".
* **Tool**: Select the newly Registered Tool from the above step.
* **Extensions**: Check off the same boxes that you selected during tool registration, Minimum: Names and Role Provisioning Services.
* **Security Settings**: All Boxes Selected except Anonymous. It may be find to have less selected, however it was tested with the described settings.
* **Make Tool Available to:**: to control access to the tool if desired to limit scope of tool to either a particular course, org wide etc. Varies depending on desired outcome.
12. Click **Create Deployment**
13. Once created, return to the deployment details of the newly created page, and at the very bottom select View Links.
    ![Config.Brightspace.3](/images/Config.Brightspace.3.png)
14. You can now create a **New Link**
* **URL**: Enter the Launch URL in here.
* Other fields as desired.

Return to the Learn LTI Tool Registration Page
15. Go to Learn LTI Application Registration Page. You will need the Output from the Tool Registration Step above.
* **Display Name**: give the tool a name of your choice. For example: "Brightspace".
* **Issuer**: enter “Issuer” from the Previous Step's output.
* **JWK Set URL**: enter “Brightspace Keyset URL” from the Previous Step's output.
* **Access Token URL**: enter “Brightspace OAuth2 Access Token URL” from the Previous Step's output.
* **Authorization URL**: enter “OpenID Connect Authentication Endpoint” from the Previous Step's output.
  Further Down..
* **Client ID**: enter “Client Id” from the Previous Step's output.
* **Audience**: enter “Brightspace OAuth2 Audience” from the Previous Step's output.
  Fill in any of the optional fields at the bottom as desired.
16. Click **Save Registration**.

You are now Ready to test/use the tool as An external tool source.
Add an External Learning Tool as content to a course. and Click the link. if your role is a Teacher then it will launch the teacher interface, and if your role is a student it will show you
no content has yet been published.

You're all set. The Learn LTI tool is now configured on your Brightspace LMS and your Educators will be able to use it to bring Microsoft Learn content to their courses. Follow the [educator guide](./USER_GUIDE.md) to create assignments that use the Learn LTI tool.

*Note: If You always see the student view in the tool and only see no content published, It is most likely because your user(s) have multiple roles assigned to them for that context. if a user is both
student and teacher role in a given course(context), then it will default to student.
