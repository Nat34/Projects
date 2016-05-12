#LAMP stack and WordPress

##Project: 
Install LAMP stack (Linux OS, Apache HTTP Server, MySQL, PHP) *Linux Mint installation not documented

##Drivers: 
* Free and open-source software
* Suitable for building dynamic websites or other web applications
* An excellent platform to deliver network services, develop all kind of dynamic or static websites, complex web applications with the help of Apache CGI

##Technology: 
Linux Mint OS, Command-line, Apache HTTP Server, MySQL, PHP, Network Config (Basic Network Configurations), APT (Advanced Packaging Tool), phpMyAdmin, filezilla

##Resources: 
TechMint, Ubuntu Wiki, Linux Mint Wiki, VimHowto

###### Install -> Test, Install -> Test

###### Verification
* Verify basic configurations like network connectivity and settings
* Verify network IP addresses using following command: 
`$ ifconfig –a`
* Verify internet connectivity: run ping command against a domain name ( this will test TCP/IP stack and DNS ). 
`$ ping –c 4 google.ro`

###### Verify machine hostname using following command:
```
$ cat /etc/hostname
$ cat /etc/hosts
$ hostname
$ hostname –f
```
###### Update system
`$ sudo apt-get update && sudo apt-get upgrade`
(refresh your package index)

###### LAMP stack (Linux-Apache-MySQL-PHP) 
* `$ sudo apt-get install lamp-server^` or
* `$ sudo apt-get install apache2 php5 php5-mysql mysql-client mysql-server` or

###### Apache
`$ sudo apt-get install apache2`
Confirm Apache installed correctly `http://localhost`
If Error: 
```
apache2: Could not determine the server's fully qualified domain name, 
using 127.0.0.1 for ServerName
```
`$ echo "ServerName localhost" | sudo tee /etc/apache2/conf.d/fqdn` (used hostname not localhost in this instance)
`sudo a2enconf fqdn` - (enable your new configuration file by running this command)
`sudo service apache2 reload` - (activate new configuration)

###### php
`$ sudo apt-get install php5 libapache2-mod-php5` (`php-pear` `php-user-cache`) suggested (what are these?)
Confirm php status: Create a `info.php` file in `/var/www/html` server path with the following content: `<?php phpinfo(); ?>`
1. Create info.php outside this directory first
2. `$ sudo mv info.php /var/www/html` sudo allows authorized users to run certain programs, etc as root
3. Open a browser and enter your server IP address or `http://server_address/info.php`

###### Display Recently Installed Software
`cat /var/log/dpkg.log | grep “\ install\ “`


###### phpMyAdmin
`$ sudo apt-get install phpmyadmin` Confirm with `http://server_address/phpmyadmin/`

###### Using Apache
* Access apache by typing http://localhost/
* Read [ApacheMySQLPHP](https://help.ubuntu.com/community/ApacheMySQLPHP)

###### vim
`sudo apt-get install vim`
`vim`
`:q!`
`vimtutor`

###### WordPress + LAMP purpose
* After LAMP stack install you will now have a new folder called `/var/www/`. This is where you will put your site, i.e use the LAMP stack to run a local version of Wordpress on the machine; install the latest version of Wordpress right in the folder `/var/www/` then build the site and test various code changes and plugins "before" uploading to sFTP

###### WordPress (local LAMP Installation)
1. Install LAMP
2. Enable the Universe repository
	* Adding the Universe and Multiverse Repositories:
	* `sudo cp /etc/apt/sources.list /etc/apt/sources.list.backup`
	* `/etc/apt/sources.list`
3. `sudo apt-get install wordpress`
4. `sudo ln -s /usr/share/wordpress /var/www/html/wordpress`
5. `sudo apt-get install mysql-server`
6. `sudo gzip -d /usr/share/doc/wordpress/examples/setup-mysql.gz`
   `sudo bash /usr/share/doc/wordpress/examples/setup-mysql -n wordpress` localhost
7. Moving a Root install to its own directory (www.example.com for example)

###### WordPress Remote Installation
1. Download WordPress
2. Unzip WordPress
3. Upload using (s)FTP - filezilla
4. setup a database
5. WordPres install script @ http://www.yoursitename.com/wordpress
6. Need to know: database name, username, pw, and database host name (which will save inside the wp-config.php file).
7. Manually create file: https://codex.wordpress.org/Editing_wp-config.php
8. This file `wp-config.php` is located in the root of your WordPress file directory and contains your website's base configuration details, such as database connection information.

###### Site Accessibility
* W3C’s “Web Content Accessibility Guidelines 1.0”, Level “A”
* Simple and Consistent - "use simple information architecture with uniform navigation and reliable headings throughout. Content layout and graphical design are consistent on every page."
* Main Site Navigation and Sub-content - Location consistent on every page with sub-content contained within accordian drop-downs

###### Common FTP Commands
```
bye to exit the FTP environment
cd  to change directory on the remote machine
get  to copy one file from the remote machine to the local machine
help to request a list of all available FTP commands
lcd to change directory on your local machine (same as UNIX cd)
ls to list the names of the files in the current remote diretory
```





