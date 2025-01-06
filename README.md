<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2-pro-g2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6


<h2>Installation Steps</h2>


1.)To get started, head over to https://portal.azure.com/ to create your virtual machine. Choose Windows 10 Pro, version 22H2 for the operating system. Make sure to configure the virtual machine with at least 2 vCPUs and 16 GB of memory to ensure optimal performance.

2.)After setting up your virtual machine, you'll need to connect to it using the public IP address assigned to the VM. To do this, open the Remote Desktop Connection app on your computer and enter the public IP address to establish the connection.
</p>
<br />

<p>
<img src="https://imgur.com/MAhXK2e.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://imgur.com/Zf2jw07.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
3.)After connecting to your virtual machine, go to the Control Panel. In the Control Panel, open the "Programs" section, then click on "Turn Windows features on or off."

<p>
<img src="https://imgur.com/fGXMpx4.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/LBGkAw6.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
4.) To install and enable IIS with CGI and Common HTTP Features, follow these steps:

Open the Turn Windows features on or off window.
Expand World Wide Web Services.
Then, expand Application Development Features.
Check the boxes for:
CGI
Common HTTP Features
Click OK to apply the changes and install the necessary components for IIS.
  
<p>
<img src="https://imgur.com/LQjw9le.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/pbPeHb1.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
NOTE: Ensure that all the boxes under Common HTTP Features are checked.

To verify that IIS is installed and enabled, follow these steps:

Open a web browser of your choice.
In the address bar, type 127.0.0.1 (this is the loopback address for your local machine).
Press Enter. You should see the default IIS welcome page or something similar confirming that IIS is running.
If IIS is properly installed, it should display a page that says "Welcome to IIS" or similar.
  
<p>
<img src="https://imgur.com/eICujoq.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
  
  
5.) Now that IIS is enabled, follow these steps to install PHP Manager for IIS:

From the installation files, download PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi).
Once the file is downloaded, double-click to start the installation process.
Follow the prompts in the installation wizard to complete the installation.
After the installation is complete, PHP Manager should be ready for use with IIS.
  
6.) Next, follow these steps to install the Rewrite Module for IIS:

From the installation files, download Rewrite Module (rewrite_amd64_en-US.msi).
Double-click the downloaded file to start the installation process.
Follow the installation wizard to complete the installation.
Once installed, the URL Rewrite module will be available for use in IIS.
  
7.) To create a folder in the C drive called "PHP," follow these steps:

Open File Explorer.
Navigate to the *C:* drive.
Right-click in an empty space within the C:\ drive.
Select New > Folder.
Name the folder PHP and press Enter.
  
8.) To install PHP 7.3.8, follow these steps:

From the installation files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip).
Once the file is downloaded, right-click on it and select Extract All.
Choose the destination as C:\PHP and click Extract to unzip the contents there.
If you see a prompt asking if you want to "Keep" the file, choose Keep to retain the zip file.
Now, the PHP files should be located in C:\PHP.
  
<p>
<img src="https://imgur.com/xZv1Yhw.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/YwBhqo0.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

9.) After extracting the PHP zip file into the C:\PHP folder, follow these steps to install the Visual C++ Redistributable:

From the installation files, download VC_redist.x86.exe.
Double-click the VC_redist.x86.exe file to start the installation.
Follow the prompts in the setup wizard to complete the installation.
Once the installation is complete, restart your computer if prompted to ensure all components are properly installed.
This will set up the necessary runtime for PHP to work correctly on IIS.
  
10.) To install MySQL 5.5.62, follow these steps:

Download MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the installation files.
Double-click the mysql-5.5.62-win32.msi file to start the installation.
In the setup wizard, choose Typical Setup and proceed.
Once the installation is complete, ensure that Launch Configuration Wizard is checked, then click Finish to begin the configuration process.
In the MySQL Configuration Wizard, choose Standard Configuration and proceed.
When prompted for the root password, set it as Password1.
Complete the configuration and finish the setup.
Now, MySQL should be installed and configured with your root password set to Password1.
  
<p>
<img src="https://imgur.com/KxcUy7C.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Execute the process on the next page.
  
<p>
<img src="https://imgur.com/i7sn6hT.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
11.) To open IIS as an administrator, follow these steps:

In the Windows search bar, type IIS (Internet Information Services).
Right-click on Internet Information Services (IIS) Manager from the search results.
Select Run as administrator to open IIS with administrative privileges.
The IIS Manager should open, and you should see the program interface with a list of sites and server components.
  
<p>
<img src="https://imgur.com/rgdZwmM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
12.) To register PHP in IIS, follow these steps:

In the IIS Manager, locate and click on PHP Manager in the left-hand panel under the server features.
Once the PHP Manager opens, you can proceed with registering PHP by selecting the appropriate options for configuring PHP in IIS.
This will allow you to manage PHP settings, such as version handling, configuration, and troubleshooting.
  
<p>
<img src="https://imgur.com/vvTLNBH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Register new PHP version.
  
<p>
<img src="https://imgur.com/qdbn5zQ.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
To register PHP in IIS, follow these steps:

In the PHP Manager window, click on Register PHP with IIS.
A prompt will appear asking for the path to the PHP executable file.
Navigate to C:\PHP and select the php-cgi.exe file.
Click OK to register PHP with IIS.
This will configure PHP to work with IIS.
  
<p>
<img src="https://imgur.com/oJZ0gp9.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Restart the IIS server.
  
<p>
<img src="https://imgur.com/CJ3RUbG.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
13.) To install osTicket v1.15.8, follow these steps:

Download osTicket v1.15.8 from the installation files folder.
Extract the contents of the downloaded file.
Copy the "upload" folder from the extracted files to C:\inetpub\wwwroot.
Once copied, go to C:\inetpub\wwwroot and rename the "upload" folder to "osTicket".
After the changes, go back to IIS Manager and reload IIS by selecting the server node in the left panel, then clicking Restart under the Manage server section.
This will set up osTicket on your IIS server.
  
14.) To access osTicket through IIS, follow these steps:

In IIS Manager, navigate to Sites in the left-hand panel.
Under Sites, locate and click on Default.
Inside the Default site, find osTicket in the list of applications.
On the right-hand panel, click on *Browse :80.
This will open osTicket in your web browser, allowing you to continue with the setup and configuration process.
  
<p>
<img src="https://imgur.com/Yw55d5b.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Some extensions are not enabled on the osTicket browser.
  
<p>
<img src="https://imgur.com/eJIsGTn.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
To enable PHP extensions for osTicket in IIS, follow these steps:

In IIS Manager, navigate to Sites and then click on Default.
Under the Default site, click on osTicket.
On the right-hand panel, double-click PHP Manager to open it.
In the PHP Manager, click on Enable or disable an extension.
From there, you can enable the necessary PHP extensions required for osTicket to function correctly.
  
<p>
<img src="https://imgur.com/vvTLNBH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/uigyKjb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  We will want to enable three extensions from here.
  
  1.) php_imap.dll
 
  2.) php_intl.dll
  
  3.) php_opcache.dll
  
<p>
<img src="https://imgur.com/cOem7Nb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
To rename the configuration file and adjust permissions for osTicket, follow these steps:

Open File Explorer and navigate to C:\inetpub\wwwroot\osTicket\include.
Locate the file ost-sampleconfig.php and rename it to ost-config.php.
After renaming, right-click on the ost-config.php file and select Properties.
In the Properties window, click on the Security tab.
Click on Advanced to open the advanced security settings.
In the Advanced Security Settings, find the Inheritance section at the bottom and click on Disable inheritance.
Select Remove all inherited permissions from this object.
This will ensure that the file has its own security settings, removing any inherited permissions.
  
  Now we will add new permissions.
  
  Click Add
  
<p>
<img src="https://imgur.com/VPZvOdo.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Select a principal
  
<p>
<img src="https://imgur.com/PoGk34d.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
 Type "Everyone" in the box.
  
<p>
<img src="https://imgur.com/F4H3ppM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Make sure Full Control and all the other boxes are checked.
  
<p>
<img src="https://imgur.com/rbbGqwB.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Click Apply and Ok.
  
<p>
<img src="https://imgur.com/saRO3y5.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
 To continue setting up osTicket and configure the database:

On the osTicket browser page, click Continue.
Fill out the setup page as required, except for the Database Settings section at the bottom. You can leave that for later.
Next, download and install HeidiSQL:

Go to the installation files and download HeidiSQL.
Once downloaded, run the installer and follow the setup wizard to complete the installation of HeidiSQL.
HeidiSQL will be used to manage your MySQL database and connect it to osTicket.
  
<p>
<img src="https://imgur.com/i7a4gWC.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  When the program is open we will create a new session in it.
  
<p>
<img src="https://imgur.com/g5M1i61.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  We want to make sure the username is root and the password is Password1.
  
<p>
<img src="https://imgur.com/LEAZNOc.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  To finish setting up osTicket and configure the database, follow these steps:

Connect to HeidiSQL:

Open HeidiSQL and connect to your MySQL session.
Create a New Database:

On the left side of the HeidiSQL interface, right-click where it says "Unnamed".
Select Create new and then choose Database.
Name the new database osTicket and click OK to create the database.
Return to the osTicket Setup:

Go back to the browser where you were setting up osTicket.
Under the Database Settings, enter the following:
Username: root
Password: Password1
MySQL Database: osTicket
Click Continue to proceed with the osTicket setup.

This will link osTicket to the newly created database and finish the installation process.
  
<p>
<img src="https://imgur.com/0rG1AJm.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  

<p>
  
  The last step after that is to login to osTicket on the browser.
  
<p>
<img src="https://imgur.com/uHVdDsx.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Congrats! You have now successfully installed and setup osTicket!

