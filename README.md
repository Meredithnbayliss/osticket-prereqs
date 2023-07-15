<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

In this tutorial, I will outline the prerequisites and installation for osTicket, a widely-used open source help desk support ticketing system. 

This process involves three main procedures including: 
    
    1.) Creating a virtual machine in Azure
   
    
    2.) Installing OsTicket Requirements 
    
    
    3.) Installing OsTicket itself
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create a Virtual Machine in Azure
- Install Web Server Installer 
- Install osTicket 
- Install HeidiSQL
- Complete OsTicket Installation 

<h2>Installation Steps</h2>

In Step 1: We create a Resource Group inside Azure.

<p>
<img src="https://i.imgur.com/NLmkO3I.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In step 2, we create a Windows 10 Virtual Machine (VM) with 2-4 virtual CPU's inside Azure. We will also allow the Virtual Machine to create a new virtual network (Vnet). We will then create a username and password of our choice. This username and password will be used for the Remote Desktop function we are using to access the virtual machine we just created. 
</p>
<br />

<p>
<img src="https://i.imgur.com/zUJXPhs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In step 3, we open the Remote Desktop Connection app on our computer. A remote desktop is an internet-enabled program or operating system feature that lets someone access a computer from a different location, just as if they were interacting with the device locally. We will be using this to connect to the Virtual Machine we created in Azure. 
</p>
<br />

<p>
<img src="https://i.imgur.com/gjCqlbo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<img src="https://i.imgur.com/7rFwxkw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
In step 4, we install / Enable IIS in Windows. IIS is a web server that OS Ticket runs on. Go to your Search Bar > Type "Control Panel" > Click "Programs" > "Turn Windows features on or off" > Scroll down to "Internet Information Services (IIS).

</p>
<br />
<img src="https://i.imgur.com/N10VQV5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
In step 5, we check that IIS is installed properly. Then we install  MySQL 5.5, which will be used as the database OSTicket operates with. We will add credentials to access this software by using the username: root and password of our choice.
</p>
<br  />
</p>
<img src="https://i.imgur.com/els5NeM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<img src="https://i.imgur.com/u1Cm2YT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
In step 6, we Fix any failures if required. Then we install a few more tools required to prepare the framework for OsTicket to operate correctly. We install PHP Version 7.3.8, Install Microsoft Visual C++ 2009 Redistributable Package (if necessary).
and Install PHP Manager 1.5.0 for IIS 10. We Register PHP from within IIS. Then, we Reload IIS, and restart the server
</p>
<br />
<img src="https://i.imgur.com/VGmw14Z.png" alt="Disk Sanitization Steps"/>
</p>
<br />
<img src="https://i.imgur.com/dyAWT6J.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
In Step 7, we download OsTicket v1.15.8. We Download osTicket from the Installation Files Folder. Then we Extract and copy “upload” folder to c:\inetpub\wwwroot
and Within c:\inetpub\wwwroot, we Rename “upload” to “osTicket”
</p>
</p>
<br />
<img src="https://i.imgur.com/3irPmfV.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<img src="https://i.imgur.com/AClNLPE.png" alt="Disk Sanitization Steps"/>
</p>
<br />
<img src="https://i.imgur.com/mgKYLDf.png" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
Im step 8, we TheReload IIS (Open IIS, Stop and Start the server). Next, we Go to sites -> Default -> osTicket
On the right, click “Browse *:80”
you should see OS Ticket installer running 
</p>
</p>
<br />
<img src="https://i.imgur.com/ycv6kbK.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
<img src="https://i.imgur.com/gRyUNTe.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
<img src="https://i.imgur.com/acaPPwi.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
In step 9, we Note that some extensions are not enabled. to enable them, 
Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
</p>
</p>
<br />
<img src="https://i.imgur.com/dahz2DQ.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
<img src="https://i.imgur.com/YMYmSiN.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
Refresh the osTicket site in your browse, observe the changes
</p>
</p>
<br />
<img src="https://i.imgur.com/uJCI4mj.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
In step 10, We Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
</p>
<br />
<img src="https://i.imgur.com/1Ve7bvD.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
In step 11, we Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All
</p>
</p>
<br />
<img src="https://i.imgur.com/wMA08IR.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
<img src="https://i.imgur.com/MR66gSA.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
<img src="https://i.imgur.com/aFv2vCI.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
In step 12, Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)
</p>
</p>
<br />
<img src="https://i.imgur.com/kBUcPwX.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
<img src="https://i.imgur.com/pyr9YHW.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
In step 13, From the Installation Files, download and install HeidiSQL.
Open Heidi SQL
Create a new session, root/Password1
Connect to the session
Create a database called “osTicket”
</p>
</p>
<br />
<img src="https://i.imgur.com/SBFVQaE.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
<img src="https://i.imgur.com/wvALons.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
<img src="https://i.imgur.com/DE7QMnc.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
In step 14, we Continue Setting up osticket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: Password1
Click “Install Now!”
</p>
</p>
<br />
<img src="https://i.imgur.com/dxBgE4R.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
<img src="https://i.imgur.com/tUHjPH7.png" alt="Disk Sanitization Steps"/>
</p>
</p>
<br />
In step 15, Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

End Users osTicket URL:
http://localhost/osTicket/ 

pic

Step 16, Clean up
Delete: C:\inetpub\wwwroot\osTicket\setup
Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Notes:
Browse to your help desk login page: http://localhost/osTicket/scp/login.php  
End Users osTicket URL: http://localhost/osTicket/ 


