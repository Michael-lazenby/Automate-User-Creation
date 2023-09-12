

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
<img src="https://i.imgur.com/r5R5wN1.png" height="80%" width="80%" alt="AD tennant"/>
<h2>Step 2: Creating an Azure Logic App</h2>
<p>Head to the Logic App section via the Azure portal and click “Add.” We must place the logic app inside a subscription and a resource group. We will also need to name our logic app, and you should name it something easily identifiable.
</p>
<img src="https://i.imgur.com/IIVcCyf.png" height="80%" width="80%" alt="designer"/>


<h2>Creating virtual machines</h2>


<br />

<h2>Wireshark installation and observation</h2>
<p>
Before I started the lab I installed Wireshark. I observed network traffic with Wireshark, and I was also able to filter ports by using the filter bar. For example, I filtered ICMP(Internet Control Message Protocol) and viewed traffic between my virtual machines when I sent ping requests to the Ubuntu VM. After sending one ping request I sent a continuous ping request to the Ubuntu VM.
</p>
<br />

<p>
<img src="https://i.imgur.com/SDL7FsW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<h2>Blocking inbound ports with port security rules</h2>
<p>
The next step of my project was to stop the continuous ping requests from my Windows VM. I did this by adjusting the inbound port rules for my Ubuntu VM via the Network Security Group settings, and I denied traffic from the ICMP port. This allowed me to observe the ping requests timing out, and I didn't receive a response from the VM. </p>
<img src="https://i.imgur.com/vbtVvOi.png" width="80%" alt="Disk Sanitization Steps"/>
<br />
<h2>Other port practice</h2>
<h3>Connecting with SSH</h3>
<p>
I connected to the Ubuntu VM using SSH. While connected to the Ubuntu VM I created a new directory using the mkdir command and added a file to the directory using the touch command. 
<img src="https://i.imgur.com/4RHnH8G.png" width="80%" alt="Disk Sanitization Steps"/>
<h3>DNS traffic monitoring</h3>
<p>
I used nslookup to send a DNS request to Google. Google's DNS server responded with IPv6 and IPv4 addresses .</p>
<img src="https://i.imgur.com/UB7QZNv.png" width="80%" alt="dns"/>

<br />
<h2>Alternative method to filter ports via Wireshark</h2>
<p>
I also learned a different method to filter ports in Wireshark. The other way to filter ports is by typing the network protocol and the port you are trying to filter. I have listed examples below:</p>

- tcp.port == 22
- udp.port == 53

<br />
<h2>Conclusion</h2>
<p> Overall this lab was insightful because it allowed me to visualize network traffic through different protocols. It allowed me to tinker with different settings and gain hands-on experience. It is important to read how network protocols work, but the hands-on experience reinforces the concepts I have been learning about. </p>
