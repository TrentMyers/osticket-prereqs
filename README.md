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

<p> <h4> Navigate to your search bar and search for "control panel" > "Programs" > "Turn windows features on or off"
</h4> </p>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/4b81c8ef-3542-4a21-930a-eba8002410a0)

<p> <h4> Check the box next to "IIS (Internet Information Services)". </h4>
</p> 

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/973f4709-cea2-4565-9b3f-52049a5a7315)



<p> <h4> Expand "IIS" and navigate to "World Wide Web Services". > Expand "World Wide Web Services" and navigate to "Application Development Features". > Expand "Application Development Features" and check the box next to "CGI".</h4> </p>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/60c1d392-5b89-44ee-9fdd-0c281f6debba)


<p> <h4>Collapse "Application Development Features". > Expand "Common HTTPS Features" and ensure that everything is selected. > Press OK to save changes. </h4> </p>


<p>


<b> <i> Install the necessary software from the following links and ensure that you have administrative privileges to install these components: </i> </b>

<li> PHP Manager for IIS: https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10 </li>
<li> Rewrite Module: https://download.microsoft.com/download/D/8/1/D81E5DD6-1ABB-46B0-9B4B-21894E18B77F/rewrite_x86_en-US.msi </li>
<li> VC_redist.x86.exe: https://aka.ms/vs/17/release/vc_redist.x86.exe </li>
<li> PHP (Not to be confused with PHP Manager): https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=sharing </li>
<i> <b> [ When installing PHP, create a directory (folder) in the root of your drive and name it "PHP". Unpack/Unzip your PHP download into your new "PHP" directory. ] </b></i>
<li> MySQL: https://dev.mysql.com/get/Downloads/MySQLInstaller/mysql-installer-web-community-8.0.36.0.msi </li>
<i><b> [ Once you finish the installation, it will prompt you with a few options so be sure you select Standard installation > install as a window service > create your root password > Execute. ] </b></i>

</p>
<p>
<h4> Open IIS as an admin and Navigate to PHP Manager</h4>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/be7f97ba-abb7-492e-aa9e-db414f25e519)

<h4> Click on "Register new PHP version", browse your drive for the "PHP" folder we created earlier and select php.cgi</h4>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/da6a989d-7e75-4cde-9c15-32d5ea3b269d)

<h4> restart IIS to ensure the changes are made.</h4>
</p>
