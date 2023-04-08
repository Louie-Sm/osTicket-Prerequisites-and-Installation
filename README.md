<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

 

<h2>Description</h2>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure Virtual Machine
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- Link to downloads: https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Environments Used </h2>
<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
<h2> Setup process </h2>

<p>
<img src="https://i.imgur.com/OtNxGkK.png" height="80%" width="80%" alt="control panel setup Steps"/>
Step 1
</p>
<p>
First you will need to run control panel as an admin in order to enable IIS(internet information services) inside of windows programs with CGI.
</p>
<br />

<p>
<img src="https://i.imgur.com/3nxkQGN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 2
</p>
<p>
You can test to make sure everything is enabled by typing in 127.0.0.1 into your web browser and you should be greeted with the above page. If you get an error message or page not found, go back and make sure all programs match the ones enabled in the previous image.
</p>
<br />

<p>
<img src="https://i.imgur.com/B6p9Bro.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/IQmAbsy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 
</p>
<p>
Now that IIS is installed and enabled next is to download and install some of the prerequisite programs needed in order to operate OS Ticket Such as PHP manager and Rewrite module
</p>
<br />

<p>
<img src="https://i.imgur.com/6VsgfMZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 4
</p>
<p>
After installing PHP manager and before installing the remaining prerequisites we need to create the Directory folder C:\PHP in our desktops files explorer.
</p>
<br />

<p>
<img src="https://i.imgur.com/s7UXG2Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 5
</p>
<p>
We will then be extracting all of the contents of the PHP.7.3.8 prerequisite file into our newly created PHP Directory In C:\PHP
</p>
<br />

<p>
<img src="https://i.imgur.com/s6yPLSd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 6
</p>
<p>
Next install the prerequisite program file Microsoft Visual C++ Redistributable
</p>
<br />

<p>
<img src="https://i.imgur.com/27wJKIi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 7
</p>
<p>
The next step is to install the MySQL Server program as a typical setup type, what this will do is install a database on the machine for OS ticket to store application data such as tickets and users. 
</p>
<br />

<p>
<img src="https://i.imgur.com/ZhUIqL6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 8
</p>
<p>
After you finish the installation it will launch the MySQL Instance configuration wizard which you will use to create a standard configuration 
</p>
<br />

<p>
<img src="https://i.imgur.com/lWt0hNi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 9
</p>
<p>
Leave configuration settings the same and enter a root password, be sure to make not of these credentials.
</p>
<br />

<p>
<img src="https://i.imgur.com/txxES5x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 10
</p>
<p>
Next we will open IIS as an admin and using the PHP manager we installed we will register a new PHP version that will be located in the C:\PHP directory we extracted our PHP.7.3.8 prerequisite files to you will then select and open “php-cgi”.
</p>
<br />

<p>
<img src="https://i.imgur.com/Z5kcs71.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/ozv7jcp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 11
</p>
<p>
Next we will install OS ticket by first downloading the osTicket-v1.15.8 Zip file and extracting the “upload” folder within it into C:\intepub\wwwroot you will then rename the “upload” folder to “osTicket” once completed restart IIS using the actions tab.
</p>
<br />

<p>
<img src="https://i.imgur.com/Co0hp81.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 12
</p>
<p>
Using the IIS manager click on the Drop down menu for your machine and go to “view Sites” in the actions tab that opens up on the right hand side. From there you will need to navigate the drop down menu to “default web site” then drop down and select “osTicket” and click on the “browse *:80(http)” circled in the image above
</p>
<br />

<p>
<img src="https://i.imgur.com/ZOmRDSb.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 13
</p>
<p>
Note that some extensions are not enabled on the osTicket installer page
We must head back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browse to observe the changes
</p>
<br />

<p>
<img src="https://i.imgur.com/H8Uy6uw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 14
</p>
<p>
Now we need to rename the ost-sampleconfig.php file From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<br />

<p>
<img src="https://i.imgur.com/GhePmWd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/zxehXfG.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 15
</p>
<p>
Through option clicking on properties we will need to Assign Permissions to ost-config.php  by selecting security and selecting the advanced option “Disable inheritance” -> Remove all inheritance, once disabled set new Permissions by clicking “add” then “select a principal” and type in everyone to inheritance with full control.

</p>
<br />

<p>
<img src="https://i.imgur.com/lRo0Ai0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 16
</p>
<p>
Next we need to download and install HeidiSQL before continuing with the osTicket setup in our browser, be sure to log in using the same root and password credentials you created when we installed the mySQL Server program.
</p>
<br />

<p>
<img src="https://i.imgur.com/yeY1Afu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/RCI6yxI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 17
</p>
<p>
Using HeidiSQL, we will create a new database named “osTicket” by right clicking “unnamed” and selecting “Create new”-> “Database”
</p>
<br />

<p>
<img src="https://i.imgur.com/bC9oicj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 18
</p>
<p>
We will then proceed with the installation process for OS ticket through the browser we opened earlier. You can fill in the appropriate information and then enter the Database connection information as followed
MySQL Database: osTicket
MySQL Username: root
MySQL Password: (password credentials you created)
Click “Install Now!”
</p>
<br />

<p>
<img src="https://i.imgur.com/OGgxvI5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 19
</p>
<p>
Congratulations your ticketing system should now be fully installed.
</p>
<br />

<p>
<img src="https://i.imgur.com/YE0uCUq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/oLf4AZP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
Step 20
</p>
<p>
Now for Clean up!

Delete the setup file in C:\inetpub\wwwroot\osTicket\setup
Then return to the properties for ost-config.php and set Permissions to “Read” and “Read and execute” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
</p>
<br />

