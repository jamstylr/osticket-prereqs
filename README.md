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

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/30dfbd48-be11-436a-bc78-606c4a85b912)
<p>
To begin, create a Windows 10 Pro Virtual Machine on Azure with 2-4 vcpus (Virtual CPUs). During the setup process, make sure to enable the creation of a new Virtual Network (VNet) for connectivity. Afterwards, connect to the VM using its Public IP Address.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/a2b16f4a-d625-4359-a44b-f616b58c61fc)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/a48d7de0-a8aa-4911-a2e7-f7474bb50add)
<p>
Once you have connected to your VM, you will want to go to Control Panel->Programs->Turn Windows Features On/Off. From there, access Internet Information Services (IIS) and ensure that CGI and Common HTTP Features are enabled. Within the Internet Information Services folder, go to Worldwide Web Services->Application Development Features-> and enable CGI. Also, inside the Worldwide Web Services folder, expand Common HTTP Features and make sure everything here is enabled. To confirm that IIS is properly installed and enabled, open a web browser and search for 127.0.0.1; you should see Internet Information Services displayed.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/9f8c6e29-11fb-4908-a6bb-e5c027f23c38)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/1a13467a-78c3-4ce9-8927-bd0d19f0b507)
<p>
Next, navigate to the Installation Files Folder and download PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) followed by the Rewrite Module (rewrite_amd64_en-US.msi), then proceed to install both files.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/6559e00b-2c40-4dfb-87a5-b8114471a36a)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/2bbd3f3d-c5be-4890-93e9-3040fc28b862)
<p>
Next, create a new folder/directory named "PHP" in the Windows (C:) drive, so that the location of the folder is “C:\PHP”. Then, from the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents (extract all) into the newly created "C:\PHP" folder.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/f161e809-2ab0-42ac-bd48-f1014ae93d4b)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/77370024-96b8-4d8b-ba46-4d1c025535a2)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/f3879f78-d223-427a-97c6-d4929599fe09)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/3bc88ba3-f89f-4a2e-83a2-1bc9b0ce3054)
<p>
From the Installation Files Folder, download and install VC_redist.x86.exe. Then download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi). In the MySQL Setup Wizard, choose “Typical” Setup Type and Launch Configuration Wizard (after install). In the MySQL Configuration Wizard, select "Standard Configuration" and set a new root password, such as "Password1" or any other preferred password. The username will be “root”.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/bcc6f1cd-7116-40a8-8bdb-575b91aefa6d)
<p>
Next, search for "IIS" in the Windows search bar, then right-click "Internet Information Services (ISS) Manager" and select "Run as Administrator".
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/99467fa5-c4a5-437b-a289-ddca07b5af3a)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/2215e2ae-ecc9-48a5-b98a-5828c19bf0cb)
<p>
In the ISS Manager, open "PHP Manager" and proceed to "Register New PHP Version”. Then, locate and select the PHP CGI executable file (php-cgi.exe) from the PHP folder you created earlier (C:\PHP).
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/f771749c-ee41-4c24-a842-b0541e7541a9)
<p>
In the Internet Information Services Manager window, click on "Restart" to reload the IIS Server, located under "Manage Server".
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/e06fe46a-8f6a-4636-a10d-ca0daf4b5065)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/2f6c6605-fb39-4587-91c6-303c2e1aab24)
<p>
Download "osTicket v1.15.8.zip" from the Installation Files Folder. Extract the contents and copy the "upload" folder. Paste the "upload" folder into "C:\inetpub\wwwroot". Rename the "upload" folder to "osTicket". Return to the Internet Information Services Manager window and click on "Restart" to reload the IIS Server once more.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/16041207-9c34-4d8a-9f6e-7b3b7caaef5f)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/2f30c67a-9758-439d-87b6-d6accaf78a88)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/f0f99f41-65d7-40c9-8be5-17d3eacf3420)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/ed9af397-0a57-4ac8-9c53-80385f56f366)
<p>
Inside IIS Manager go to Sites-> Default-> osTicket. On the right, click on “Browse*:80(http)". You will now see the osTicket installer and notice that some extensions are not enabled. You will need to enable these extensions in the IIS console before installing osTicket. To enable these extensions, go back to IIS Manager, then navigate to Sites-> Default-> osTicket-> PHP manager-> PHP Extensions - "Enable or disable an extension”. From here you will want to enable three extensions: php_imap.dll, php_intl.dll, php_opcache.dll. Refresh the osTicket Installer in the web browser to confirm that these extensions are now enabled.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/5d978fac-bd79-4fef-b9e8-eb2ff55334a3)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/01d2641a-84aa-4b4e-a373-c5f60822e81e)
<p>
Now that you have those extensions enabled in IIS, you need to rename one of the files in the osTicket folder and change its permissions before continuing to install osTicket. Open File Explorer and search for “C:\inetpub\wwwroot\osTicket\include” and rename “ost-sampleconfig.php” to “ost-config.php”.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/16e99bd1-1c4b-4dd5-ab89-002f53426895)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/dde19a3e-9724-4a0c-94ea-76b637c03ba2)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/6854219d-5a08-4ca8-82dd-944eba93f300)
<p>
Once you've renamed the file, right-click on it and select "Properties". In the Properties window, navigate to the "Security" tab and click on "Advanced". A new window will open named "Advanced Security Settings for ost-config.php”, select "Disable inheritance” and then choose "Remove all inherited permissions from this object". After this, go back to the "Advanced Security Settings" window and click "Add", click "Select a principle" in the next window, and in the window after that type in "Everyone" in the box. Click “Check Names” and then click “Ok”. In the "Permission Entry" window, select “Full Control” and make sure all other permissions are selected and click “Ok”. Finally, in the "Advanced Security Settings" window, click "Apply" and then "Ok".
</p>

<p>
After you've completed those steps, proceed with setting up osTicket in your browser. Click "Continue" on the osTicket browser page. Fill out the necessary fields on the page, excluding the Database Settings section at the bottom. You'll address this later. The default email address is the one that receives emails from customers. Do not click "Install" yet, as you'll require additional SQL information before proceeding.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/d1824082-4d8f-4e25-a5bb-9ab9cb3447de)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/a9ef419c-e52a-4d83-b54f-e9684374c41f)
<p>
From the Installation Files Folder, download and install HeidiSQL. HeidiSQL is used to manage and interact with the MySQL database, which is necessary for configuring and setting up osTicket. Open HeidiSQL and click "New" in the bottom left corner to create a new session. Enter the username “root” and the password “Password1” (or the password that you used earlier in the installation of MySQL) and then click “Open”.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/a3528068-6849-4bf8-8523-94a22948e842)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/7c623622-7568-4cdd-aca3-287087788408)
<p>
In the new HeidiSQL window you will now create a new database by right clicking "Unnamed" on the left -> Create new-> Database. Name this Database "osTicket" and click “Ok”.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/fc7e7a83-819b-438b-ab05-5372f80380b8)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/3c1b4c62-b5c5-4efe-bdb1-e7418fa96d9d)
<p>
You can now go back to the osTicket installation form and fill out the remaining information required by typing "osTicket" in MySQL Database, "root" in MySQL Username, and “Password1" (or your chosen password) in MySQL Password. Then, click "Install Now”.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/56c32208-dff0-4fae-973a-cd6d20c2c089)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/34fee002-ca42-4781-a1aa-e8a8b0d0baaf)
<p>
For the final step, you will need to do some clean up. Open File Explorer and go to C:\inetpub\wwwroot\osTicket\ and delete the "setup" folder. Then go into the "include" folder and change the permissions for "ost-config.php". You will do this the same as before: Right click-> Properties-> Security tab-> Advanced-> Open the Allow Everyone tab under Permission entries-> Check only “Read” and “Read & Execute”-> Ok-> Apply-> Ok.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/6027a3ee-ff55-4dd3-94d3-442e642e38d0)
<p>
osTicket Help Desk Login Page : http://localhost/osTicket/scp/login.php
</p>
<p>
osTicket End User Page: http://localhost/osTicket/
</p>
<br />
