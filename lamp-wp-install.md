## LAMP stack and WordPress

### Project: 
Install LAMP stack (Linux OS, Apache HTTP Server, MySQL, PHP)

### Drivers: 
All of these components are free and open-source software, they are suitable for building dynamic websites or other web applications, and they are the most used platforms on the Internet today.  An excellent platform to deliver network services, develop all kind of dynamic or static websites, complex web applications with the help of Apache CGI, all of this made with a minimum financial impact using Free and Open Source software and the latest technologies.

### Technology: 
Linux Mint OS, Command-line, Apache HTTP Server, MySQL, PHP, Network Config (Basic Network Configurations), APT (Advanced Packaging Tool), phpMyAdmin

### Resources: 
TechMint, Ubuntu Wiki, Linux Mint Wiki, VimHowto

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

##### LAMP stack (Linux-Apache-MySQL-PHP) 
`$ sudo apt-get install lamp-server^`
`$ sudo apt-get install apache2 php5 php5-mysql mysql-client mysql-server`
* Confirm php status create a ‘info.php‘ file in ‘/var/www/html’ server path with the following content: `<?php phpinfo(); ?>` Create info.php outisde this directory first then `$ sudo mv info.php /var/www/html` sudo allows authorized users to run certain programs, etc as root

* open a browser and enter your server IP address or `http://server_address/info.php`

###### phpMyAdmin
`$ sudo apt-get install phpmyadmin` Confirm with `http://server_address/phpmyadmin/`

###### Using Apache
* Access apache by typing http://localhost/
* READMORE(ApacheMySQLPHP)[https://help.ubuntu.com/community/ApacheMySQLPHP]

###### vim
`sudo apt-get install vim`
`vim`
`:q!`
`vimtutor`

###### WordPress (local LAMP Installation)
1. Install LAMP
2. Enable the Universe repository
	1. Adding the Universe and Multiverse Repositories:
	2. `sudo cp /etc/apt/sources.list /etc/apt/sources.list.backup`
	3. /etc/apt/sources.list
3. `sudo apt-get install wordpress`
4. `sudo ln -s /usr/share/wordpress /var/www/html/wordpress`
5. `sudo apt-get install mysql-server`
6. `sudo gzip -d /usr/share/doc/wordpress/examples/setup-mysql.gz`
   `sudo bash /usr/share/doc/wordpress/examples/setup-mysql -n wordpress` localhost
7. Moving a Root install to its own directory (www.example.com for example)





