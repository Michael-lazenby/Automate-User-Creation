

<p align="center">
<img src="https://i.imgur.com/hvR1GC5.png" alt="Azure Logic App"/>
</p>

<h1>Azure Logic Apps: Automating the onboarding process</h1>
<h2>Overview</h2>
In this project, we are going to automate the process of onboarding a new user into Azure AD. We will utilize the Azure Logic apps to create and design our workflow. This project is entry-level, and you do not need advanced knowledge about the Azure ecosystem.
<h2>What are Azure Logic Apps?</h2>
Azure Logic apps are a low-code or no-code solution, and they are helpful when trying to automate organizational processes with predefined connectors made by Microsoft. For example, an organization might need to trigger an event when an email is received, and this is something complex to do while writing your own code, but Microsoft’s connectors make this a simple process.

<h2>Steps</h2>

- Create a new Azure AD Instance
- Logic App Workflow design
- Create an Azure AD user
- Monitoring and Review


<h2>Step 1: Creating a new Azure AD tenant</h2>

<p>When creating a new Azure AD tenant, navigate to Azure Active Directory, click on Manage tenants, and click Create. We must fill out the basic information like our organization’s name and domain. After we click on Review + Create, it will take a few minutes to populate.</p>
<img src="" height="80%" width="80%" alt="AD tennant"/>

<h2>Step 2: Creating an Azure Logic App</h2>

<p>Head to the Logic App section via the Azure portal and click “Add.” We must place the logic app inside a subscription and a resource group. We will also need to name our logic app, and you should name it something easily identifiable.
</p>
<img src="https://i.imgur.com/kiaFAGZ.png" height="80%" width="80%" alt="logicappcreation"/>
<p>Then, we will click “Review + Create.” We will be redirected back to the Logic App directory, and then we will navigate to our newly created app. Once inside, click the “Logic app designer,” where we will start designing our workflow.</p>
<img src="https://i.imgur.com/IIVcCyf.png" height="80%" width="80%" alt="logichome"/>


<h2>Step 3: Logic App workflow</h2>
<p>Click on “Create a workflow in Designer,” and it will prompt us to create a new workflow, as seen below.</p>
<img src="https://i.imgur.com/RBIS7Vn.png" height="80%" width="80%" alt="neworkflow"/>
<p>Name the workflow; once again, it is essential to name it something recognizable. We also have the option to choose a state type, and we will select “Stateful.” We choose stateful in this scenario because our app will deal with inputs and outputs that change the state. After we fill out that information, we will press “Create,” once the app has rendered, click on the app’s name, and it will redirect us to our logic apps workflow page.</p>
<img src="https://i.imgur.com/tqQOjuH.png" height="80%" width="80%" alt="neworkflow"/>
<p>Click on “Edit in Designer” and select “Get started”. You will be taken to the logic app designer page.</p>
<img src="https://i.imgur.com/AYzolyH.png" height="80%" width="80%" alt="neworkflow"/>
<p>Once you’re inside the designer page, click “Add a trigger,” this is how we will start designing our application. A trigger is an input and output event. Click on the trigger and search for HTTP. We are going to select “When an HTTP request is received.” You will also need to fill out the JSON schema, which you can do with a JSON convertor. If you have never used a JSON converter, click here for a simple convertor.</p>
<img src="https://i.imgur.com/EHar0p4.png" height="80%" width="80%" alt="neworkflow"/>
<img src="https://i.imgur.com/aSsZzkR.png" height="80%" width="80%" alt="neworkflow"/>
<p>We will then click on the “+” and add another action. The action we will be adding is to “create a user.” We will fill out the basic information for the user provided to us via the HTTP request: the user’s first and last name, phone number, display name, Mail Nickname, Password, and the user principal name(UPN). You will fill out the fields by clicking on them and selecting “Dynamic content” or “Expression.” The Dynamic content is the information from the HTTP request, and the expressions are essential functions Microsoft provides.</p>
<img src="https://i.imgur.com/0sONn5t.png" height="80%" width="80%" alt="neworkflow"/>
<p>You can create the display name however you would like, but most organizations combine the employee’s first and last name. You will also need to create a password that can be a statically typed or a dynamic password. The User Principle name must be another combination of the first and last name or another unique identifier your organization uses for their employees.</p>
<p>Click on “+” again to add another step, and we will search for “Add user to group,” as shown below.</p>
<img src="https://i.imgur.com/OkLG0Wa.png" height="80%" width="80%" alt="neworkflow"/>
<p>Once we click the “Add user to group” action, fill out the required information, as shown below.</p>
<img src="https://i.imgur.com/AH6LsoB.png" height="80%" width="80%" alt="neworkflow"/>
<p>Add the Group ID. The group ID information is in the Groups section in the Azure portal, and you will copy and paste the group ID. We created the user ID in the previous step. You must click inside the “User ID” box, and another box will appear with dynamic content options. You will choose “ID”, as shown below.</p>
<img src="https://i.imgur.com/DdlLoKU.png" height="80%" width="80%" alt="neworkflow"/>
<p>After filling out the information to add a user to the group, we have one more step to add to our logic app: to send an email notifying you that a new user has been created. Click on the “+” to add another step, and this time we will search for “Send an email.” You can choose from various email providers, but using your Outlook email will be more straightforward for this project. You will be prompted to fill out the information for your email, as seen below.</p>
<img src="https://i.imgur.com/TN2VGQ2.png" height="80%" width="80%" alt="neworkflow"/>
<p>You can put any information you want to include in the body and the subject line. You must also choose who you want to send the confirmation email to. You have completed your logic app, and now it is time to test it to see if it is working correctly.</p>
<img src="https://i.imgur.com/QTDn0n2.png" height="80%" width="80%" alt="neworkflow"/>
<h2>Step 4: Testing the Logic app</h2>
<p>In the Logic app designer page, navigate to the top and click “Run Trigger,” A drop-down menu will appear, and click “Run with payload.” You will prompted to fill out the JSON to create your user.</p>
<p>Note — You can use a different method to test the HTTP request if you would like, but I choose to use the testing method within Azure just because it’s more convenient. You can use services like Postman if you prefer a different service than Azure.</p>
<img src="https://i.imgur.com/gj7V2Yf.png" height="80%" width="80%" alt="neworkflow"/>
<p>Once you click “Run,” it will trigger your application, and you can see if the event was successful in the overview section of our Logic app.</p>
<img src="https://i.imgur.com/2PNnTh0.png" height="80%" width="80%" alt="neworkflow"/>
<p>If it states that your trigger was successful in the overview page, you can navigate to the users and groups section to verify the user was made correctly and added to the right group.</p>
<img src="https://i.imgur.com/QS0D3oY.png" height="80%" width="80%" alt="neworkflow"/>
<img src="https://i.imgur.com/TRVcd7f.png" height="80%" width="80%" alt="neworkflow"/>
<p>The last step is verifying that you received an email with a user’s creation notification. Head over to your email and ensure you received it; if you did, it indicates that your Logic app is working correctly.</p>
<img src="https://i.imgur.com/CekRpIK.png" height="80%" width="80%" alt="neworkflow"/>

<h2>Congratulations!</h2>
<p> You have successfully created your first Azure Logic App. You have learned the basic process of creating an Azure Logic App, and you can do many more amazing things with it. I would recommend continuing to practice and creating other Logic apps for other processes that can be automated.

</p>
