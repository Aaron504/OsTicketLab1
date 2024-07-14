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

- Setup a Virtual Machine in Azure
- Install the osTicket Requirements
- Install the osTicket itself
- Do the after-installation configuration of osTicket
- Explore osTicket as a Help Desk Professional
- Create, Interact, and Close Tickets

<h2>Installation Steps</h2>

Virtual Machine Created
![Screenshot 2024-07-13 152900](https://github.com/user-attachments/assets/7e794449-327a-4fd0-b18a-e673f5ce972c)

Logging into the VM with RDP to start our installation process.
![Screenshot 2024-07-13 154634](https://github.com/user-attachments/assets/fbc8a099-77f8-4f7d-9995-8bad8c8ca0ab)

We will install/enable IIS in Windows with CGI and Common HTTP Features.
![Screenshot 2024-07-13 162130](https://github.com/user-attachments/assets/e675d703-c85c-41f9-9615-7fff4c457288)

From the Installation Files, I will now download and install PHP Manager for IIS
![Screenshot 2024-07-14 101106](https://github.com/user-attachments/assets/7afbbe51-e412-485a-a4eb-ffbe58b9cca3)

From the Installation Files, download and install the Rewrite Module
![Screenshot 2024-07-14 102321](https://github.com/user-attachments/assets/e60638b3-4df2-4c12-9332-30859aeb2925)

Now I will Create the directory C:\PHP then From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
![Screenshot 2024-07-14 103124](https://github.com/user-attachments/assets/261d662b-f0b5-4dd3-b607-64a6a390898b)
![Screenshot 2024-07-14 104054](https://github.com/user-attachments/assets/b7b869f4-d36b-4b7a-98af-32fb34ce3774)
![Screenshot 2024-07-14 104318](https://github.com/user-attachments/assets/08a515f7-5eed-417e-8bb5-e0da950941dd)

From the Installation Files, I will download and install VC_redist.x86.exe.
![Screenshot 2024-07-14 105044](https://github.com/user-attachments/assets/cc7a6636-a07d-46ed-8685-5048542dc866)

From the Installation Files, I will download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
![Screenshot 2024-07-14 105737](https://github.com/user-attachments/assets/ba9840d1-309c-4c29-aa39-90b893aa8d65)

Now I will Open IIS as an Admin, Register PHP from within IIS, and Reload IIS (Open IIS, Stop and Start the server)
![Screenshot 2024-07-14 112834](https://github.com/user-attachments/assets/c9954bfa-9c62-4605-b011-851aac18b025)

Download osTicket from the Installation Files Folder
Extract and copy “upload” folder to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

![Screenshot 2024-07-14 115743](https://github.com/user-attachments/assets/8e8f12be-f47b-432c-8b43-10fec8b9ec93)
![Screenshot 2024-07-14 120358](https://github.com/user-attachments/assets/227d8938-1302-4e63-a837-15f5976d19ba)

Now I will Reload IIS (Open IIS, Stop and Start the server), Go to sites -> Default -> osTicket, and On the right, click “Browse *:80”
![Screenshot 2024-07-14 121449](https://github.com/user-attachments/assets/65365ba1-118c-482c-9a7a-93fc638417be)

Note that some extensions are not enabled
- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”
- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll
- Refresh the osTicket site in your browse, observe the changes

  ![Screenshot 2024-07-14 122508](https://github.com/user-attachments/assets/6d7654c2-525a-49ac-b654-ee9be07aa867)
  ![Screenshot 2024-07-14 122659](https://github.com/user-attachments/assets/e3547fca-3c07-491b-aac4-22a5e3360fe9)

Rename: ost-config.php
- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
![Screenshot 2024-07-14 123439](https://github.com/user-attachments/assets/9682ecd7-39f7-4a90-8ebf-5b8da9578298)

Assign Permissions: ost-config.php
- Disable inheritance -> Remove All
- New Permissions -> Everyone -> All
![Screenshot 2024-07-14 124102](https://github.com/user-attachments/assets/cd7d2a82-3a46-4beb-ac2f-2fbeb37f1d69)

Continue Setting up osTicket in the browser (click Continue)
- Name Helpdesk
- Default email (receives email from customers)
![Screenshot 2024-07-14 124929](https://github.com/user-attachments/assets/97097a23-94ea-434f-b0a8-45c9e212c4f7)

From the Installation Files, download and install HeidiSQL.
- Open Heidi SQL
- Create a new session, root/Password1
- Connect to the session
- Create a database called “osTicket”
![Screenshot 2024-07-14 125504](https://github.com/user-attachments/assets/efa66066-ea72-4ca5-8c54-6d112f75f8e6)
![Screenshot 2024-07-14 130047](https://github.com/user-attachments/assets/05e4a6f4-d2fb-400f-b1eb-205af31227e8)
![Screenshot 2024-07-14 130527](https://github.com/user-attachments/assets/173375d4-9fc6-4f23-abab-66c1c164adcb)
![Screenshot 2024-07-14 131053](https://github.com/user-attachments/assets/66150681-eafa-42f6-b503-f9db9ebbaa8a)






































