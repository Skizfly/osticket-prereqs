<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this workshop, I set up osTicket from scratch by installing the required files. Before proceeding with the ticketing system installation, a series of preliminary steps need to be completed. The entire process is carried out on a Windows 10 Pro virtual machine created on Azure.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10 Pro</b> (21H2)

<h2>List of Prerequisites</h2>

- Activate Internet Information Services (IIS)
- Install PHP Manager
- Install MySQL
- Change file permissions
- Item 5

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Prior to the installation of any files, it is necessary to activate Internet Information Services (IIS). As we are installing osTicket locally, IIS is a prerequisite for its proper functioning. To enable IIS, access the Control Panel. Within the Control Panel, navigate to Programs and then Turn Windows Features On or Off. In this menu, expand Internet Information Services, further expand Web Management Tools, and activate IIS Management Console. Proceed to click and expand World Wide Web Services, and then expand Application Development Features. Within Application Development Features, enable CGI and confirm by clicking OK.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once IIS has been activated, proceed to download and install PHP Manager for IIS (PHPManagerforIIS_V1.5.0.msi) from the installation files folder. Following the installation of PHP Manager for IIS, download and install the Rewrite Module (rewrite_amd64_en-US.msi).
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After enabling IIS, it's essential to download and install PHP Manager for IIS (PHPManagerforIIS_V1.5.0.msi) from the installation files folder. Following the installation of PHP Manager for IIS, and considering that PHP is a prerequisite, download and install the Rewrite Module (rewrite_amd64_en-US.msi). 

After installing the Rewrite Module, create a new folder/directory named C:\PHP on the Windows (C:) drive. This new folder is necessary as PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) needs to be unzipped into this location. Extract all the contents from the zip folder into the C:\PHP folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Following that, proceed to download and install VC_redist.x86.exe from the installation files.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before proceeding, it's crucial to have MySQL installed as a prerequisite. Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the installation files. In the MySQL setup wizard, click "I agree," select a Typical installation, and then click Install. Once the installation is complete, launch the Configuration Wizard.

In the Configuration Wizard, choose Standard Configuration, select Install As Windows Service, and make sure to check Launch the MySQL Server automatically. For the credentials, set the username as root and the password as Password1. While it's generally advisable to use more secure credentials in real-world scenarios, for the purposes of this lab, the standard credentials root and Password1 will be used.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Prior to osTicket installation, IIS configurations must be adjusted. Open IIS with administrative privileges and navigate to PHP Manager. Inside PHP Manager, choose "Register new PHP version." Utilize the Browse option to select the PHP CGI executable file (php-cgi.exe) located in the PHP folder established earlier in the lab. Once the PHP version is registered, reload the IIS server from within the management console.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Retrieve osTicket v1.15.8 from the installation files. Unpack the contents and copy the "upload" folder. Paste the "upload" folder into the directory: c:\inetpub\wwwroot. Inside the c:\inetpub\wwwroot folder, rename the "upload" folder to "osTicket." Following these steps, reload the IIS server.</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate to the IIS console and go to Sites -> Default -> osTicket. Click "Browse *:80," and the osTicket installation page will be accessible. Before installing osTicket, ensure that some extensions are enabled within the IIS console. While in the osTicket menu in IIS, click on PHP Manager. Choose "Enable or disable an extension" and activate the following extensions: php_imap.dll, php_intl.dll, php_opcache.dll.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
As a prerequisite to continuing with the osTicket installation, it's essential to manage file permissions. Begin by navigating to C:\inetpub\wwwroot\osTicket\include. Within this directory, rename ost-sampleconfig.php to ost-config.php. Following the renaming, adjust the permissions for ost-config.php. Open its Properties and perform the following steps: Disable inheritance -> Remove All, and in New Permissions -> Everyone -> All. These permission adjustments are crucial for the proper functioning of osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Retrieve HeidiSQL from the installation files and install it. Establish a new session in HeidiSQL, entering the MySQL installation password when prompted. In the new session, right-click on "Unnamed" and generate a new database named osTicket.Retrieve HeidiSQL from the installation files and install it. Establish a new session in HeidiSQL, entering the MySQL installation password when prompted. In the new session, right-click on "Unnamed" and generate a new database named osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the osTicket browser window, input the required information to configure osTicket. Use the same credentials as those employed for MySQL and HeidiSQL when setting up the MySQL database.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Upon completion of the installation process, osTicket is now ready for use! However, before proceeding, it's important to perform some cleanup tasks. Firstly, remove the setup folder located in C:\inetpub\wwwroot\osTicket. Subsequently, return to C:\inetpub\wwwroot\osTicket\include and adjust the permissions of the ost-config.php file. The file should no longer grant full access to Everyone; instead, revert the permissions to "Read" only.
</p>
<br />

<p>
<h1>osTicket Installed</h1>
</p>
<p>
osTicket has been successfully installed and is now prepared for utilization. I employed osTicket as a learning tool to gain insights into ticketing systems, understanding their functionalities, and mastering the resolution of tickets. In the field of IT Support, collaboration within a team is essential to address individuals' IT-related concerns through the systematic use of a ticketing system. This lab served as a foundational step, allowing me to establish a ticketing system from the beginning and lay the groundwork for my future endeavors in this domain.
</p>
<br />
