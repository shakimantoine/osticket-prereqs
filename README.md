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



<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 1 – Create and Connect to Your VM

In Azure, create a Windows 10 VM with:

Name: osticket-vm

Size: 4 vCPUs

Username: labuser

Password: osTicketPassword1!

Use Remote Desktop to connect to the VM.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 2 – Prepare the VM Environment

Download osTicket-Installation-Files.zip to the VM desktop and unzip.

Install IIS with CGI enabled:

World Wide Web Services → Application Development Features → ✅ CGI.

From the installation folder:

Install PHP Manager and Rewrite Module.

Create directory C:\PHP.

Extract PHP 7.3.8 into C:\PHP.

Install VC_redist.x86.exe.

Install MySQL 5.5.62:

Use Standard Configuration.

Username: root / Password: root.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 3 – Configure IIS and Install osTicket

Open IIS as Admin.

Register PHP: PHP Manager → C:\PHP\php-cgi.exe.

Restart IIS.

From the installation files:

Extract osTicket v1.15.8.

Copy upload folder to C:\inetpub\wwwroot and rename to osTicket.

In IIS:

Go to *Sites → Default → osTicket → Browse :80.

Enable missing PHP extensions (php_imap.dll, php_intl.dll, php_opcache.dll).

Rename config file:

C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php → ost-config.php.

Set permissions on ost-config.php:

Disable inheritance → Remove All.

Add Everyone → Full Control.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 4 – Finalize osTicket Setup

In browser setup:

Helpdesk name & default email.

Install HeidiSQL:

Create new session (root/root).

Create database osTicket.

In browser setup:

Database: osTicket

Username: root

Password: root

Click Install Now!

Access osTicket:

Admin login: http://localhost/osTicket/scp/login.php

End-user portal: http://localhost/osTicket/


</p>
<br />
