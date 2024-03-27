<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- osTicket (open source Ticketing System)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to Installation Files: [Click here to access the installation files on Google Drive](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

<h2>Installation Steps</h2>

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/312cc62c-2636-4ed2-add5-458bb9d8b015)
<p>
To begin, create a Windows 10 Pro Virtual Machine on Azure with 2-4 vcpus (Virtual CPUs). During the setup process, make sure to enable the creation of a new Virtual Network (VNet) for connectivity. Afterwards, connect to the VM using its Public IP Address.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/03ceae9f-0d76-4c49-8cfc-7d4fb80956c7)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/4b53ef8e-dba0-4e36-a84c-9111f236e26d)
<p>
Once you have connected to your VM, you will want to go to Control Panel->Programs->Turn Windows Features On/Off. From there, access Internet Information Services (IIS) and ensure that CGI and Common HTTP Features are enabled. Within the Internet Information Services folder, go to Worldwide Web Services->Application Development Features-> and enable CGI. Also, inside the Worldwide Web Services folder, expand Common HTTP Features and make sure everything here is enabled. To confirm that IIS is properly installed and enabled, open a web browser and search for 127.0.0.1; you should see Internet Information Services displayed.
</p>
<br />



<p>
Next, navigate to the Installation Files Folder and download PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) followed by the Rewrite Module (rewrite_amd64_en-US.msi), then proceed to install both files.
</p>
<br />
