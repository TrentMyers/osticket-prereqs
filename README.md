<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket through Azure.

<h2> What is osTicket? </h2>
  
  osTicket is an open-source customer support ticketing system that enables organizations to effectively manage customer inquiries and support requests. Its primary purpose is to streamline communication between customers and support teams, allowing for efficient ticket creation, assignment, tracking, and resolution.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Personal/Work Computer
- Microsoft Azure Account https://azure.microsoft.com/en-us/ (If you want to install osTicket on your personal/Work Computer, skip Step 1)

<h2>Installation Guide:</h2>
<H2>Step 1: Set Up a Virtual Machine (VM) on Azure</H2>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/e7500c20-d8eb-4ded-8b54-0b86c8bf124a)


  <b> <i> Create a Virtual Machine in Azure.</i> </b>

<p>
 <li> Sign in to the Azure portal: Go to https://portal.azure.com/ and sign in with your Azure account. </li>

 <li> Click on the search bar (located in the top-centermost part of your screen) and search for "Virtual Machines" and create a new Azure Virtual Machine. </li>

 <li> Fill out the necessary information like name, region, and resource group.
Choose "Windows 10" as the operating system. </li>

 <li> Select an appropriate VM size and configuration (I'd recommend at least 16 GB of RAM and 2 V-CPUs)</li>

 <li> Proceed with default settings for the remaining steps or customize as needed.</li>

 <li> Click "Review + Create" and then "Create" to provision the VM.
Connect to the VM:</li>

 <li>Once the VM is provisioned, click on it in the Azure portal.
You must copy the VM's Public IP address under "Essentials".
Once copied, you will open Remote Desktop Connection on Windows and enter the credentials required to log in to your VM.
Once the VM is booted up, you will be ready for the next step.</li>
</p>

  <b> <i> Note: You must download Remote Desktop Connection if on Linux or Mac. </i> </b>



<H2>Step 2: Preparing for the Setup</H2>
 


![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/1e8a961d-2f30-42c7-b8e3-71a7320280a9)

<p> <li> Navigate to your search bar and search for "control panel" > "Programs" > "Turn windows features on or off"
</li> </p>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/672ebe75-dc15-47d0-af15-5e22cd692ec6)

<p> <li> Check the box next to "IIS (Internet Information Services)". </li>
</p> 

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/fb4c950e-68b0-47bb-a9cf-a02185d650f0)


<p> <li> Expand "IIS" and navigate to "World Wide Web Services". > Expand "World Wide Web Services" and navigate to "Application Development Features". > Expand "Application Development Features" and check the box next to "CGI".</li> </p>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/fa4bb02b-eff1-400f-b9c8-ce48b2e30268)

<p> <li>Collapse "Application Development Features". > Expand "Common HTTPS Features" and ensure that everything is selected. > Press OK to save changes. </li> </p>


<p>


<b> <i> Install the necessary software from the following links and ensure that you have administrative privileges to install these components: </i> </b>

<li> PHP Manager for IIS: https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view?usp=share_link </li>
<li> Rewrite Module: https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=share_link </li>
<li> VC_redist.x86.exe: https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=share_link </li>

</p>

<H2> Step 3: Setup </H2>
<p>

</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
<H2>Step 4:</H2>
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
