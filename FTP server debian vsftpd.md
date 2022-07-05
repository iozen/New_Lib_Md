
FTP Server Installation on Debian

Follow the below steps for installing VSFTPD-Very secure FTP Daemon on the Debian OS.
Step 1: Installing VSFTPD

Launch the Terminal in your Debian OS by going into the Activities tab on the top left corner for your desktop. Then in the search bar, type terminal. When the Terminal icon appears, click on it to launch it.

Then in the Terminal, type the following command to update the repositories.

$ sudo apt-get update

When prompted for the password, type sudo password.

Update Packages

Then execute the below command in Terminal to install VSFTPD package:

$ sudo apt-get install vsftpd

Installing vsftpd

Once the installation is completed, you can check the version of VSFTPD package by running the following command in Terminal:

$ vsftpd -versions

check vsftpd version
Step 2: Enable and start VSFTPD service

VSFTPD service does not start automatically upon the installation. To start VSFTPD service, run the following command in Terminal:

$ systemctl start vsftpd

The system will prompt for user authentication. Enter the password and click Authenticate.

To enable vsftpd service to always start at the boot time, run the following command in Terminal.

$ systemctl enable vsftpd

The system will prompt several times for user authentication. Enter the password and click Authenticate.

Start vsftpd
VSFTPD Configuration

Now we will perform some configurations required for setting up FTP server in our Debian OS.
Step 1: Allow ports in Firewall

If you are running firewall, then allow ports 20 and 21 for FTP using the following commands:

$ sudo ufw allow 20/tcp

$ sudo ufw allow 21/tcp

Open FTP port in the firewall

Once done, confirm it by checking the status of the firewall using the following command:

$ sudo ufw status

Check Firewall status
Step 2: Configuring FTP Access

Before making any changes to the VSFTPD configuration file, make sure to back up the original vsftpd.config file. For that, you can use the following command.

$ sudo cp /etc/vsftpd.conf /etc/vsftpd.conf.orig

Configure FTP

Now run the following command in Terminal to edit the vsftpd.config file in nano editor. You can use any editor for this purpose.

$ sudo nano /etc/vsftpd.conf

Add the following lines at the end of the file:

listen=NO
listen_ipv6=YES
anonymous_enable=NO
local_enable=YES
write_enable=YES
local_umask=022
dirmessage_enable=YES
use_localtime=YES
xferlog_enable=YES
connect_from_port_20=YES
chroot_local_user=YES
secure_chroot_dir=/var/run/vsftpd/empty
pam_service_name=vsftpd
rsa_cert_file=/etc/ssl/certs/ssl-cert-snakeoil.pem
rsa_private_key_file=/etc/ssl/private/ssl-cert-snakeoil.key
ssl_enable=Yes
pasv_enable=Yes
pasv_min_port=10000
pasv_max_port=10100
allow_writeable_chroot=YES
ssl_tlsv1=YES
ssl_sslv2=NO
ssl_sslv3=NO

Once done, press Ctrl+O and Ctrl+X to save and exit the file.

vsftpd.conf configuration file
Step 3: Restart the VSFTPD service

To apply the configuration changes made above, you will need to restart the vsftpd service. Run the following command to do so:

$ sudo systemctl restart vsftpd

Step 4: Create an FTP user

Now we will need to create ftp user that will be allowed to connect to ftp server.

Enter the below command to create a user:

$ sudo useradd -m <user_name>

Then assign a to the above-created user using the following command:

$ sudo passwd <user_name>

In the following example, we have created a user with the name ftpuser and assigned a password to it.

Create an FTP user
Test the FTP Connection

To test the FTP connection, you will need to install FTP client in the same or a separate system from where you want to access the FTP server. In our case, we are using FileZilla as an FTP client.

Run the following command in the Terminal to install FileZilla.

$ sudo apt-get install filezilla

Once the installation is completed, open FileZilla either using the Terminal or from the Dash menu. when opened, enter required information like hostname/IP address, user name, and password and click the Quickconnect button.

Test FTP Connection by using FileZilla

Verify the certificate and click OK to connect to the FTP server.

Accept SSL certificate

You will be successfully logged in to the FTP server and able to available access files and directories of the remote server.

FTP connection successful

Now that you have installed and set up the FTP server, you can now use it for transferring files from your local machine to the remote FTP server and vice versa.