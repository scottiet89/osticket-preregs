<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Microsoft Azure Part 1: Prerequisites and Installation](https://youtu.be/Skud9OEovqw)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create a Resource Group in Microsoft Azure
- Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs within the Resource Group you created
- Have this link to the [osTicket Installation Files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) open and ready to paste into your Windows 10 Virtual Machine

<h2>Installation Steps</h2>

<p>
After completing the prerequesites above open your Microsoft Azure Windows 10 virtual machine via "Remote Desktop Connection".
Simply copy and paste your virtual machines public IP address and login using the username and password you provided Azure.
</p>
<p>
<img src="https://i.gyazo.com/367b7bc5367ef6a9f58ad01867971fef.png">
</p>
<br />

<p>
Next we have to install and enable Internet Information Services (IIS) in Windows with CGI. To do this, open the Control panel and click "Programs", then click "Turn Windows features on or off". Next check each of the features exactly like in one of the images below, in the order of "World Wide Web Services" -> "Application Development Features" -> check "CGI", and then press "OK". 

Once the installation is finished open Microsoft Edge and type and enter 127.0.0.1 into the search bar, if the IIS page appears that means that everything was installed correctly.
</p>
<p>
<img src="https://i.imgur.com/IQH33cf.png">
<img src="https://i.imgur.com/p7TsqoH.png">
<img src="https://camo.githubusercontent.com/27dacaaa327beb3d34eba9fefa06ee647f5340d4289770b3bde0c042d8233440/68747470733a2f2f692e696d6775722e636f6d2f37475646734d4e2e706e67"/>
<img src="https://i.imgur.com/syVKVO4.png">
</p>

<p>
Now within the VM open this link (https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6). This is going to provide all of the installation files we need in order to install osTicket.
  
Download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) from the Installation Files.
<img src="https://i.imgur.com/b4K90DP.png">

Download and install the Rewrite Module (rewrite_amd64_en-US.msi) from the Installation Files.
<img src="https://i.gyazo.com/a0e9c68340ab1e7e6c046d9030d76db9.png">
  
Create a folder named "PHP" in the location C:\PHP
<img src="https://i.gyazo.com/029bcb938fb400c7b03836cab8d63150.png">
  
Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) from the Installation Files and unzip the contents into C:\PHP.
<img src="https://i.gyazo.com/14855f2802e4a90b0d7e18c057bb4c29.png">
<img src="https://i.gyazo.com/9c9c967a17559e45a8134e6435259a7e.png">
<img src="https://i.gyazo.com/912b26f2e87cf1627f2e3a23d1d92e3a.png">
  
Download and install VC_redist.x86.exe from the Installation Files.
<img src="https://i.gyazo.com/be0375247a2c0e5aa9215fc50fe5c64a.png">

Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the Installation Files. During the installation process, select "Typical Setup", then launch the Configuration Wizard (after installation) and select "Standard Configuration" with the password as "Password1".
<img src="https://i.gyazo.com/943c13b4805569234fbaae63156748eb.png">
<img src="https://i.gyazo.com/07a7de5cf1ce3efa83d95b9168eed72d.png">
<img src="https://i.gyazo.com/4578a4201546941acfab6ce3923631d4.png">
<img src="https://i.gyazo.com/f7857f33a399c5492eedaa644e4ae6a0.png">
<img src="https://i.gyazo.com/e6721a1a99ee461c50ba94520a3e4e3a.png">  
  
Open IIS as an Admin and register PHP from within IIS.
<img src="https://i.gyazo.com/93c4a3ec8a09046039bb007b0aa9d588.png">
<img src="https://i.gyazo.com/f6c789ca23a21e99af894c6e85b3e128.png">
<img src="https://i.gyazo.com/fd6c837a883ed1b17abb00af4892e0bb.png">

<p>Reload IIS (Open IIS, Stop and Start the server).</p>
<img src="https://i.gyazo.com/86285f2b8b2d653c687f3b4b4ff5ed40.png">
</p>

Install osTicket v1.15.8. Download osTicket from the Installation Files Folder, extract and copy the "upload" folder to c:\inetpub\wwwroot. Within c:\inetpub\wwwroot, rename "upload" to "osTicket".
<img src="https://i.gyazo.com/10db29676bd6bf7bebe7b88004caee40.png">
<img src="https://i.gyazo.com/2f1d1924bcf67fa1b632a13ed6cbb32e.png">
<img src="https://i.gyazo.com/b5519a9c510f93b366361d991da76b68.png">
<img src="https://i.gyazo.com/48f6b0b3aa63c8c8c535da64d001bbb7.png">
<img src="https://i.gyazo.com/dd2b3fc029b777b97e1b0ed8b1bb7656.png">
<p>Reload IIS (Open IIS, Stop and Start the server)</p>
<img src="https://i.gyazo.com/f4ddd49848cca4b5c12746d58f9c2d27.png">

Go to sites -> Default -> osTicket. On the right, click "Browse *:80" to open the osTicket site. Note that some extensions are not enabled.
<img src="https://i.gyazo.com/234776513ac0bf7020151f154b3e3568.png">
<img src="https://i.gyazo.com/fb9ec6919de67dce639c5341536492eb.png">
<img src="https://i.gyazo.com/529c109a5d65030dd986e1bfcadc7128.png">

<p>Go back to IIS, sites -> Default -> osTicket. Double-click PHP Manager, then click "Enable or disable an extension". Enable the following extensions: php_imap.dll, php_intl.dll, php_opcache.dll.</p>
<img src="https://i.gyazo.com/fd9712a5a576e8eb9d940595dc58b51d.png">
<img src="https://i.gyazo.com/685abe3674de537d8390e8e5e7cafb38.png">
<img src="https://i.gyazo.com/3dc8db4040086de220cc14f9a159bee1.png">
<img src="https://i.gyazo.com/b2b55a555ad5118b476be4b365d78675.png">
<img src="https://i.gyazo.com/281b58d87cba1089bb922dee9eea3031.png">

Refresh the osTicket site in your browser and observe the changes.
<img src="https://i.gyazo.com/1045dfd05ce33c23e0fb4dd3a849231a.png">

Rename "ost-sampleconfig.php" to "ost-config.php" from C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php. 
Next assign permissions to "ost-config.php". Disable inheritance, then remove all existing permissions. Add new permissions for "Everyone" and give them "All" access.
<img src="https://i.gyazo.com/006ea8148836f968c01527a3c2ce6032.png">
<img src="https://i.gyazo.com/8e0cefc85dff5769d4757bd8ff7736ed.png">
<img src="https://i.gyazo.com/def3f685bd70b33d95cb1ae2e688a085.png">
<img src="https://i.gyazo.com/56616ef3f64bc3576b3f8b361e357499.png">
<img src="https://i.gyazo.com/303707513b24c9154513005a58a757a2.png">

<p>Continue setting up osTicket in the browser by clicking "Continue". Name the helpdesk and provide the default email address that will receive email from customers.</p>
<img src="https://i.gyazo.com/50260ade7d5608972b3e2c7cd54ef8ab.png">
<img src="https://i.gyazo.com/7aa04d4ae54b33331d2e832aff85b712.png">

<p>Download and install HeidiSQL from the Installation Files. Open HeidiSQL, create a new session with root/Password1, and connect to the session. Create a database called "osTicket".</p>
<img src="https://i.gyazo.com/55e5e23ac5bcdb8fc88f7cf57bcb0216.png">
<img src="https://i.gyazo.com/f22cd5bfa5a4a3b9e806efcd27c66d3b.png">
<img src="https://i.gyazo.com/f9a89629cd9605e79d3d4843ddcf216f.png">
<img src="https://i.gyazo.com/bd0c062d060c04ca16f02e2f60d5438a.png">
<img src="https://i.gyazo.com/5ae3a5d945a187ed9056ebbcea5105b5.png">

<p>Continue setting up osTicket in the browser by entering the following details: MySQL Database: osTicket, MySQL Username: root, MySQL Password: Password1. Click "Install Now!".</p>
<img src="https://i.gyazo.com/d42a08bd64fbfbdfcb859af42ae80411.png">

<p>Congratulations! osTicket is now installed on your Windows 10 Azure Virtual Machine.</p>
<img src="https://i.gyazo.com/1df948cd32a1b557d555eeb2de7e1e6a.png">

Extra steps and notes:

Delete: C:\inetpub\wwwroot\osTicket\setup and Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
<img src="https://i.gyazo.com/c10280d6b6c7129c46aa3089723f635e.png">
<img src="https://i.gyazo.com/1135011e0b92559a065b99ceefde0717.png">

Notes:
Browse to your help desk login page: http://localhost/osTicket/scp/login.php  
End Users osTicket URL: http://localhost/osTicket/ 
