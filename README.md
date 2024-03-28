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

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/c10091d4-ae48-4d74-9531-bac7d732e294)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/52d68fde-0117-4f35-b6a3-0c38681ebe67)
<p>
Next, navigate to the Installation Files Folder and download PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) followed by the Rewrite Module (rewrite_amd64_en-US.msi), then proceed to install both files.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/bc23a0fb-397d-44c7-96f3-c6d0ffbe789c)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/91866cb7-1cab-4b94-9f23-6b2e60def29a)
<p>
Next, create a new folder/directory named "PHP" in the Windows (C:) drive, so that the location of the folder is “C:\PHP”. Then, from the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents (extract all) into the newly created "C:\PHP" folder.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/35730c06-c11f-4742-93a3-34aab0aa706b)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/89a75de4-2dbe-43c0-bbb5-e83a82ad061e)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/21a71271-1006-4d64-87c3-277134880aac)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/27688437-6a9c-4f1a-8954-a9b582072fbe)
<p>
From the Installation Files Folder, download and install VC_redist.x86.exe. Then download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi). In the MySQL Setup Wizard, choose “Typical” Setup Type and Launch Configuration Wizard (after install). In the MySQL Configuration Wizard, select "Standard Configuration" and set a new root password, such as "Password1" or any other preferred password. The username will be “root”.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/ff5cccfc-7080-4726-b18b-b636a612affa)
<p>
Next, search for "IIS" in the Windows search bar, then right-click "Internet Information Services (ISS) Manager" and select "Run as Administrator".
</p>
<br />


<p>
In the ISS Manager, open "PHP Manager" and click on "Register New PHP Version”. Then select “Browse” and choose the PHP CGI executable file (php-cgi.exe) located within the PHP folder you created earlier (C:\PHP\php-cgi.exe).
</p>
<br />
