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

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- CGI
- IIS
- C++ Redistributables
- Item 4
- Item 5

<h2>Virtual Machine</h2>

<p>

</p>
<p>
Before we can begin using osTicket, we have to create and log into a virtual machine using Microsoft Azure. Log in via remote desktop and, using the VM, download and unzip osticket. (Make sure your VM is using Windows 10 22h2 and 2 VCPUs with 8Gb of RAM each at least) 
</p>
<br />

<p>
<blockquote class="imgur-embed-pub" lang="en" data-id="a/fwAamS5" data-context="false" ><a href="//imgur.com/a/fwAamS5"></a></blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script>
</p>
<h2>IIS and CGI</h2>
<p>
Inside your VM, open the control panel. Then open "Programs". Under Programs, select "Turn Windows features on and off" to access IIS and CGI. From here, make sure that Internet Information Services (IIS), Application Development Features, CGI, World Wide Web Services, and all Common HTTP features are selected.     
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h2>PHP Manager and MySQL</h2>
<p>
From within the osTicket installation files, download the PHP Manager, rewrite module, C++ redistributables, and MySQL. After downloading the PHP Manager, create a folder on your C drive at C:/PHP and extract it there. After installing MySQL, select "typical setup" when prompted and launch the configuration wizard. Within the wizard, select standard configuration and create a memorable root password. Execute the wizard.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h2>IIS Manager</h2>
<p>
Now, in the Windows search bar, type IIS and open Internet Information Services Manager as an administrator. Open the PHP manager inside the IIS Manager and register your PHP version installed in C:/PHP. After doing this, stop and start the IIS server to reload it. 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h2>Install osTicket</h2>
<p>
To install osTicket, extract the zipped folder on the C drive. Inside the unzipped osTicket folder, there is a file named upload. Copy that file into the folder named “c:\inetpub\wwwroot”. Then, rename the "upload" file to "osTicket".
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h2>IIS Permissions</h2>
<p>
Navigate back to the IIS Manager. Reload IIS. Underneath connections on the left-hand side of the IIS manager, select sites, default, then osTicket. On the right, under "Manage Folder", select “Browse *:80”. This will load the osTicket site. Go back to IIS and Sites-->Default Sites-->osTicket. Select the PHP manager within osTicket. Select "Enable and Disable PHP Extensions. Enable php_imap.dll, php_intl.dll, php_opcache.dll. Refresh the osTicket site to ensure that everything is enabled. 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h2>IIS Permissions cont.</h2>
<p>
Rename the ost config file, which can be found in C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php. Rename ost-sampleconfig.php to ost-config.php. After renaming the file, right-click it and go to 
properties-->Security-->Advanced. Select Disable inheritance to first remove all permissions. Add new permissions and type "everyone" into the text box. Select ok, full control, and ok again. This will allow osTicket to have full control over the configuration file. In the osTicket browser, enter the helpdesk name you want and the email you'll use to receive mail from customers. 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h2>HeidiSQL and osTIcket setup</h2>
<p>
From the osTicket installation folder on the C drive, install and launch HeidiSQL. Within the HeidiSQL session manager, create a new session and login with the password you created when setting up MySQL. Inside the session, create a database named "osTicket". In the osTicket browser, enter the MySQL database, username, and password, and click install now. 
</p>
<br />
