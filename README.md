
<!-- How to install and configure OpenLDAP Server on Ubuntu   By Garima -->



<!-- Check host name and ip of system -->

$ hostname 
garima-Default

$ hostname -f
$ ifconfig

% Step 1 - Prerequisites

% Apply these below commands in your terminal 

sudo apt install apache2 php php-cgi libapache2-mod-php php-mbstring php-common php-pear -y
	
sudo apt install slapd ldap-utils -y

% add password to admin entry 

% install LDAP Account Manager (LAM)
sudo apt -y install ldap-account-manager

//Steps

sudo apt update


=== Install OpenLDAP ===

sudo apt install slapd ldap-utils

===    Configure OpenLDAP ===

sudo dpkg-reconfigure slapd

=== Install phpLDAPadmin: ===

sudo apt install phpldapadmin

===  Configure phpLDAPadmin:  ===

sudo vi /etc/phpldapadmin/config.php


Find the line that begins with $servers->setValue('server','host', and set the value to 'localhost'.

Find the line that begins with $servers->setValue('server','base', and set the value to your LDAP base DN. For example:

===
$servers->setValue('server','base',array('dc=example,dc=com'));
$config->custom->appearance['hide_template_warning'] = true;
===

===  Restart Apache Web Server:  ===

sudo systemctl restart apache2


http://ip/phpldapadmin

===  How to you Local to ServerMove file commands lines ===

sudo scp -i /home/ubuntu/keypath/"keyname"  /home/ubuntu/filepath/"filename"   ubuntu@178.08.09803:/home/ubuntu

=== How to server to local move file commands ===

sudo scp -i /home/ubuntu/keypath/"keyname" ubuntu@178.08.09803:/home/ubuntu/filepath/"filename"   /home/user/localpath/download/


== issue ===

sudo ufw allow "OpenLDAP LDAP"


== phpmyadmin upload size incress conf ===

sudo vi /etc/php/8.1/apache2/php.ini
max_execution_time = -1
max_input_time = -1
memory_limit = -1
post_max_size = 4000G 
upload_max_filesize = 3000G

===

cd /usr/share/phpldapadmin/

mv  htdocs htdocs.old
mv lib  lib.old

After 

local to move this file  -- htdocs and lib file 

== link Atached description ==






