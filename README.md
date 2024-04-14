<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
<p>This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket through Azure.</p>

<h2>What is osTicket?</h2>
<p>osTicket is an open-source customer support ticketing system that enables organizations to effectively manage customer inquiries and support requests. Its primary purpose is to streamline communication between customers and support teams, allowing for efficient ticket creation, assignment, tracking, and resolution.</p>

<h2>Environments and Technologies Used</h2>
<ul>
  <li>Microsoft Azure (Virtual Machines/Compute)</li>
  <li>Remote Desktop</li>
  <li>Internet Information Services (IIS)</li>
</ul>

<h2>Operating Systems Used</h2>
<p><strong>Windows 10 (21H2)</strong></p>

<h2>List of Prerequisites</h2>
<ul>
  <li>Personal/Work Computer</li>
  <li>Microsoft Azure Account (Visit <a href="https://azure.microsoft.com/en-us/" target="_blank">Microsoft Azure</a>. If you want to install osTicket on your personal/work computer, skip Step 1.)</li>
</ul>

<h2>Step 1: Set Up a Virtual Machine (VM) on Azure</h2>


<p><strong><em>Create a Virtual Machine in Azure.</em></strong></p>
<ul>
  <li>Sign in to the Azure portal: Go to <a href="https://portal.azure.com/" target="_blank">https://portal.azure.com/</a> and sign in with your Azure account.</li>
  <li>Click on the search bar (located in the top-centermost part of your screen) and search for "Virtual Machines" and create a new Azure Virtual Machine.</li>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/e7500c20-d8eb-4ded-8b54-0b86c8bf124a)
  
  <li>Fill out the necessary information like name, region, and resource group. Choose "Windows 10" as the operating system.</li>
  <li>Select an appropriate VM size and configuration (recommend at least 16 GB of RAM and 2 V-CPUs).</li>
  <li>Proceed with default settings for the remaining steps or customize as needed.</li>
  <li>Click "Review + Create" and then "Create" to provision the VM.</li>
</ul>
<p><strong>Note:</strong> Once the VM is provisioned, click on it in the Azure portal. You must copy the VM's Public IP address under "Essentials". Use Remote Desktop Connection on Windows to log into your VM. <strong> You must download virtual machine if on linux or mac.</strong></p>

<h2>Step 2: Preparing for the Setup</h2>

<p>Navigate to your search bar and search for "control panel" > "Programs" > "Turn windows features on or off".</p>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/1e8a961d-2f30-42c7-b8e3-71a7320280a9)

<p>Enable "IIS (Internet Information Services)" and within it, navigate to "World Wide Web Services". Under "Application Development Features", check the box next to "CGI". Under "Common HTTP Features", ensure that everything is selected. Press OK to save changes.</p>
<ul>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/4b81c8ef-3542-4a21-930a-eba8002410a0)

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/973f4709-cea2-4565-9b3f-52049a5a7315)

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/60c1d392-5b89-44ee-9fdd-0c281f6debba)


  <li>PHP Manager for IIS: <a href="https://www.iis.net/downloads/community/2018/05/php-manager-150-for-iis-10" target="_blank">Download here</a></li>
  <li>Rewrite Module: <a href="https://download.microsoft.com/download/D/8/1/D81E5DD6-1ABB-46B0-9B4B-21894E18B77F/rewrite_x86_en-US.msi" target="_blank">Download here</a></li>
  <li>VC_redist.x86.exe: <a href="https://aka.ms/vs/17/release/vc_redist.x86.exe" target="_blank">Download here</a></li>
  <li>PHP: <a href="https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=sharing" target="_blank">Download here</a></li>
  <i> <b> [ When installing PHP, create a directory (folder) in the root of your drive and name it "PHP". Unpack/Unzip your PHP download into your new "PHP" directory. ] </b></i>
  <li>MySQL: <a href="https://dev.mysql.com/get/Downloads/MySQLInstaller/mysql-installer-web-community-8.0.36.0.msi" target="_blank">Download here</a></li>
<i><b> [ Once you finish the installation, it will prompt you with a few options so be sure you select Standard installation > install as a window service > create your root password > Execute. ] </b></i>
</ul>

 <ul>
<li>Open IIS as an admin and Navigate to PHP Manager</li>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/be7f97ba-abb7-492e-aa9e-db414f25e519)

<li>Click on "Register new PHP version", browse your drive for the "PHP" folder we created earlier and select php.cgi</li>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/da6a989d-7e75-4cde-9c15-32d5ea3b269d)

<li>Restart IIS to ensure the changes are made.</li>

 </ul>
<h2>Step 3: osTicket Setup</h2>
<p>Install osTicket from <a href="https://github.com/osTicket/osTicket/releases/download/v1.18.1/osTicket-v1.18.1.zip" target="_blank">here</a>.</p>
<p>Once installed, open up the folder and proceed with the following steps:</p>
<ul>
  <li>Open file explorer and navigate to inetpub in your root directory.</li>
  
  ![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/e0fcf376-d7c7-4265-af3a-47e418948baa)
  
  <li>Open wwwroot and copy over the "upload" folder from your osTicket installation package.</li>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/039023b5-d44d-4678-ab37-99f75e06b0d0)

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/418b4f6d-7be6-4ef0-98c1-507d505c0d4e)

  <li>Rename the "upload" folder to "osTicket".</li>
  <li>Restart IIS to apply changes.</li>
</ul>

<ul>
<p>When IIS restarts, we will now enable the required extensions for osTicket.</p>
<li>Navigate back to PHP Manager. Look for "enable or disable an extension" and click on it.</li>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/b626bd6b-b3fa-41c8-92da-e6dc47da7208)

<p> <strong>Neable the following extensions:</strong> </p>
<li>php_imap.dll</li>
<li>php_intl.dll</li>
<li>php_opcache.dll</li>

![image](https://github.com/TrentMyers/osticket-prereqs/assets/132710625/65125ed1-2a8b-4196-bb45-9e98665eea50)


</ul>
