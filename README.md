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

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/a49ebfc7-7bbd-442d-8030-da07ba9bef06)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/88158ba9-6c2d-480f-a6d3-4cdcd15688ed)
<p>
In the ISS Manager, open "PHP Manager" and click on "Register New PHP Version”. Then select “Browse” and choose the PHP CGI executable file (php-cgi.exe) located within the PHP folder you created earlier (C:\PHP\php-cgi.exe).
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/9e4341a4-07fa-40c3-8c39-6c4988a8515f)
<p>
In the Internet Information Services Manager window, click on "Restart" to reload the IIS Server, located under "Manage Server".
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/075d07a1-045f-4dcc-bda1-c16b27d2fcce)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/19ef1a79-efa4-4f2b-b956-bda4c6787ad5)
<p>
Download "osTicket v1.15.8.zip" from the Installation Files Folder. Extract the contents and copy the "upload" folder. Paste the "upload" folder into "C:\inetpub\wwwroot". Rename the "upload" folder to "osTicket". Return to the Internet Information Services Manager window and click on "Restart" to reload the IIS Server once more.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/458cf518-5a75-4535-8f2c-907267e95657)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/8c276b5b-6e43-4826-bc85-2380af1d0070)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/c212cb1d-d09c-4e67-9b00-1aa2068ef6b9)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/a19e3718-565b-4665-8180-bb6b87c47194)
<p>
Inside IIS Manager go to Sites-> Default-> osTicket. On the right, click on “Browse*:80(http)". You will now see the osTicket installer and notice that some extensions are not enabled. You will need to enable these extensions in the IIS console before installing osTicket. To enable these extensions, go back to IIS Manager, then navigate to Sites-> Default-> osTicket-> PHP manager-> PHP Extensions - "Enable or disable an extension”. From here you will want to enable three extensions: php_imap.dll, php_intl.dll, php_opcache.dll. Refresh the osTicket Installer in the web browser to confirm that these extensions are now enabled.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/57092c6a-a873-4ef9-8273-9f0cbf3ce48d)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/acdddde9-9a3d-4c71-bc29-34c405562316)
<p>
Now that you have those extensions enabled in IIS, you need to rename one of the files in the osTicket folder and change its permissions before continuing to install osTicket. Open File Explorer and search for “C:\inetpub\wwwroot\osTicket\include” and rename “ost-sampleconfig.php” to “ost-config.php”.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/c43bcf2d-b30a-4e57-ab35-3b697af09145)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/6ccffc10-42e1-4cd7-be77-210811e49ef4)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/bc9af290-a436-4a45-bae4-971f471c8604)
<p>
Once you've renamed the file, right-click on it and select "Properties". In the Properties window, navigate to the "Security" tab and click on "Advanced". A new window will open named "Advanced Security Settings for ost-config.php”, select "Disable inheritance” and then choose "Remove all inherited permissions from this object". After this, go back to the "Advanced Security Settings" window and click "Add", click "Select a principle" in the next window, and in the window after that type in "Everyone" in the box. Click “Check Names” and then click “Ok”. In the "Permission Entry" window, select “Full Control” and make sure all other permissions are selected and click “Ok”. Finally, in the "Advanced Security Settings" window, click "Apply" and then "Ok".
</p>

<p>
Once you've completed those steps, proceed with setting up osTicket in your browser. Click "Continue" on the osTicket browser page. Fill out the necessary fields on the page, excluding the Database Settings section at the bottom. You'll address this later. The default email address is the one that receives emails from customers. Do not click "Install" yet, as you'll require additional SQL information before proceeding.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/5183b002-1419-4b4c-8f67-30dfcf6f51c2)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/effef053-57e7-491c-88fd-c6e447309e8f)
<p>
From the Installation Files Folder, download and install HeidiSQL. HeidiSQL is used to manage and interact with the MySQL database, which is necessary for configuring and setting up osTicket. Open HeidiSQL and click "New" in the bottom left corner to create a new session. Enter the username “root” and the password “Password1” (or the password that you used earlier in the installation of MySQL) and then click “Open”.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/48203bc6-8450-461e-8388-c1ee1042fe00)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/7839efb5-ca52-4edc-963b-9dfbe7417d2e)
<p>
In the new HeidiSQL window you will now create a new database by right clicking "Unnamed" on the left -> Create new-> Database. Name this Database "osTicket" and click “Ok”.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/0651534b-2bca-42be-868e-86e129ea584b)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/632ebb73-ab0b-43e3-bc48-ed01fc28ef3b)
<p>
You can now go back to the osTicket installation form and fill out the remaining information required by typing "osTicket" in MySQL Database, "root" in MySQL Username, and “Password1" (or your chosen password) in MySQL Password. Then, click "Install Now”.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/7a66aaab-0682-4669-a215-373d9e886840)
![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/73aa1372-45ce-43b8-a206-02af6938ab25)
<p>
For the final step, you will need to do some clean up. Open File Explorer and go to C:\inetpub\wwwroot\osTicket\ and delete the "setup" folder. Then go into the "include" folder and change the permissions for "ost-config.php". You will do this the same as before: Right click-> Properties-> Security tab-> Advanced-> Open the Allow Everyone tab under Permission entries-> Check only “Read” and “Read & Execute”-> Ok-> Apply-> Ok.
</p>
<br />

![image](https://github.com/jamstylr/osticket-prereqs/assets/159660523/939df60a-4c02-4d30-a5be-76c11edf54f7)
<p>
osTicket Help Desk Login Page : http://localhost/osTicket/scp/login.php
</p>
<p>
osTicket End User Page: http://localhost/osTicket/
</p>
<br />
