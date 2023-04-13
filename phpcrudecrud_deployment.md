Deployment Guide

Section #1 

The Crude CRUD Application for MariaDB enables the user to search through employee records, add employees to database records, modify employee records, delete employee records, and search employee records.

Section #2

General steps are to create an entirely new application architecture and stack from the "ground up." 

	1	Make sure the virtual machine (VM) is running on VMware or Virtual Box.

	2	Install and configure the operating system, Apache HTTP Server, and MariaDB database software on the virtual machine.

	3	This application implements the CRUD (Create, Read, Update, Delete) capabilities using the PHP programming language.

	4	Copy the repository by selecting Code and then copying the URL.
Enter the following command (git clone repoURL) into the VM and press return on Mac/enter on Windows. The directory should now be created on the VM and ready to use, with a few changes to the html file if desired.

	5	Test and the application by doing (http://yourIPAddress>/directoryName_phpcrudecrudapp>).

Section #3 - suggested Virtual Machine configuration:  disk, cpu, ram.

Use an Ubuntu 20.04 virtual machine with 1 (or 2) vCPU, 1024MB (1GB) of RAM, and a 20GB hard disk.






Section #4 - Step by step instructions on how to create a Virtualbox Virtual Machine.


	1	Download and setup VirtualBox, Visit the https://www.virtualbox.org/  website and download the appropriate OS system-compatible version. Follow the installation instructions.

	2	Launch VirtualBox by clicking on the program's desktop icon after the installation is complete.

	3	To create a new virtual machine, open the "New Virtual Machine Wizard" by clicking the "New" button in the top-left corner of the VirtualBox window.

	4	Give the virtual machine a name, Pick a name for the virtual machine on the wizard's first screen to help recognize it.

Section #5 - Step by step instructions on how to install the Ubuntu 20.04 Operating System.

	1	Download the Ubuntu 20.04 installer: https://releases.ubuntu.com/focal/ubuntu-20.04.5-live-server-amd64.iso
	2	Click the "New" button or pick Machine -> New to build a Virtual Machine.
	3	A Dialog will appear after clicking "New." Select a name for the VM in the name area. The Folder is the physical place where the files attached to the virtual machine will be stored. 
	4	Select the ISO image that was downloaded in step 1 for the ISO image.
	5	Select the "Skip Unattended Installation" checkbox.
	6	Click Next, Select 1024MB of RAM, 2vCPU’s, Next, then Finish.
	7	Go to settings->Storage->Optical Drive->select the ISO install downloaded in step 1.
	8	Start the Virtual Machine.
	9	The VM's Console will be displayed, answer the questions as they are posed. Reboot your machine. A new Ubuntu 20.04 server has been set up and is ready to go.



Section #6 - Step by step instructions on how to install Apache 2 and PHP

Update and Upgrade the server by doing the following:

$ sudo apt update
$ sudo apt upgrade

- Install Apache
	1	Log in to the Ubuntu VM and install Apache using the following:
$ sudo apt install apache2

- Install the PHP Programming Language
	1	On the VM run the following command: $ sudo apt install libapache2-mod-php
	2	Restart the Apache service to load PHP: sudo systemctl restart apache2

Section #7 - Step by step instructions on how to install MySQL

	1	Update/Upgrade system packages: $ sudo apt update && sudo apt upgrade
	2	Install MySQL: $ sudo apt install mysql-server
	3	Check the status of MySQL: $ sudo systemctl status mysql
	4	Restart the MySQL:  $ sudo systemctl restart mysql
	5	Log-in to MySQL server: $ sudo mysql -u root -p

Section #8 
Connection and credential configuration information is all stored within the phpcrudecrudapp directory and can be checked and modified as necessary, it is in (credentials.php) 
and is stored at /var/www/html.

Section #9 - Step by step instructions on how to deploy the PHP Crude CRUD Application

	1	Git clone https://github.com/Mohammedawi/mohammedawi_phpcrudecurd.git
	2	Directory will be created inside the VM.
	3	Cd phpcrudecrudapp 
	4	Copy the phpcrudecrudapp directory to /var/www/html: sudo cp * /var/www.html/
	5	Cd /var/www/html
	6	Open the browser and type in: http://<VM_ip_address>/phpcrudecrudapp
	7	Website should be displayed. 


Section #10 - Suggest system tests to run to make sure the Application is working.
Apache: Launch the browser and type in Http://<ipaddress/Address of the vm> The Default Apache web page should be displayed.

Create a new PHP file in the Apache document root directory inside ‘/var/www/html’ to ensure that PHP is installed and operating properly. You can call the file test.php or whatever you want. 
Include the following code in the file:

<?php
phpinfo();
?>

Save the file and launch the web browser. Enter the servers’ IP address, followed by the filename just created (e.g., http://server_ip/test.php). Should see a website giving information
About the PHP. 

End of guid




