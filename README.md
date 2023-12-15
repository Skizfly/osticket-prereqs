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
- Istall PHP Manager
- Item 3
- Item 4
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
