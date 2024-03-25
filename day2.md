sudo find / -type d -name 'public_html' -o -name 'html' -o -name 'www'


root@srv497201:~# cd /home/cloudpanel/htdocs
-bash: cd: /home/cloudpanel/htdocs: No such file or directory
root@srv497201:~# sudo find / -type d -name 'public_html' -o -name 'html' -o -name 'www'
/usr/lib/python3.10/html
/usr/share/doc/imagemagick-6-common/html
/usr/share/doc/varnish/html
/usr/share/doc/info/html
/usr/share/doc/iptables/html
/usr/share/nginx/html
/var/www
/var/www/html
/snap/core20/2182/usr/lib/python3.8/html
/snap/core20/2182/usr/share/doc/iptables/html
/home/clp/htdocs/app/files/public/phpmyadmin/doc/html
/home/clp/backups/2024-03-24_04-15-01/app/files/public/phpmyadmin/doc/html
root@srv497201:~# cd /var/www/html
root@srv497201:/var/www/html# ls
index.html  index.nginx-debian.html
root@srv497201:/var/www/html# cd \
>
root@srv497201:~# cd /var/www
root@srv497201:/var/www# mkdir ourbrandtv
root@srv497201:/var/www# cd ourbrandtv
root@srv497201:/var/www/ourbrandtv# nano index.php





/////////////////////////////////


root@srv497201:~# sudo nano /etc/apache2/sites-available/ourbrandtv.conf
root@srv497201:~# sudo a2ensite ourbrandtv.conf
Enabling site ourbrandtv.
To activate the new configuration, you need to run:
  systemctl reload apache2
root@srv497201:~# sudo systemctl restart apache2
root@srv497201:~# systemctl reload apache2
root@srv497201:~#



///////////////////////////////////////////////////////////////

root@srv497201:~# sudo nano /etc/apache2/sites-available/ourbrandtv.conf
root@srv497201:~# sudo a2ensite ourbrandtv.conf
Enabling site ourbrandtv.
To activate the new configuration, you need to run:
  systemctl reload apache2
root@srv497201:~# sudo systemctl restart apache2
root@srv497201:~# systemctl reload apache2
root@srv497201:~# cat /etc/apache2/sites-available/ourbrandtv.conf
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName ourbrandtv
    DocumentRoot /var/www/ourbrandtv
    <Directory /var/www/ourbrandtv>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
root@srv497201:~# ls /etc/apache2/sites-enabled
000-default.conf  ourbrandtv.conf
root@srv497201:~# sudo a2ensite ourbrandtv.conf
Site ourbrandtv already enabled
root@srv497201:~# cd  /var/www
root@srv497201:/var/www# ls
html  ourbrandtv  site
root@srv497201:/var/www# ls html
index.html  index.nginx-debian.html
root@srv497201:/var/www# ls ourbrandtv
index.php
root@srv497201:/var/www# cd ..
root@srv497201:/var# cd ..
root@srv497201:/# sudo nano /etc/apache2/sites-available/ourbrandtv.conf
root@srv497201:/# root@srv497201:/# sudo systemctl restart apache2
root@srv497201:/# sudo tail -n 50 /var/log/apache2/error.log
[Sun Mar 24 23:58:00.980379 2024] [mpm_event:notice] [pid 3683:tid 140564034148224] AH00489: Apache/2.4.52 (Ubuntu) configured -- resuming normal operations
[Sun Mar 24 23:58:00.980459 2024] [core:notice] [pid 3683:tid 140564034148224] AH00094: Command line: '/usr/sbin/apache2'
[Mon Mar 25 00:58:13.264990 2024] [core:error] [pid 22934:tid 140563928045120] [client 141.98.11.96:52286] AH10244: invalid URI path (/../../mnt/mtd/Config/Account1)
[Mon Mar 25 01:18:41.189177 2024] [core:error] [pid 22934:tid 140563818939968] [client 141.98.11.96:50152] AH10244: invalid URI path (/../../mnt/mtd/Config/Account2)
[Mon Mar 25 01:28:47.251328 2024] [mpm_event:notice] [pid 3683:tid 140564034148224] AH00492: caught SIGWINCH, shutting down gracefully
[Mon Mar 25 01:28:47.315686 2024] [mpm_event:notice] [pid 24018:tid 139864408975232] AH00489: Apache/2.4.52 (Ubuntu) configured -- resuming normal operations
[Mon Mar 25 01:28:47.315774 2024] [core:notice] [pid 24018:tid 139864408975232] AH00094: Command line: '/usr/sbin/apache2'
[Mon Mar 25 01:29:21.554486 2024] [mpm_event:notice] [pid 24018:tid 139864408975232] AH00493: SIGUSR1 received.  Doing graceful restart
[Mon Mar 25 01:29:21.559101 2024] [mpm_event:notice] [pid 24018:tid 139864408975232] AH00489: Apache/2.4.52 (Ubuntu) configured -- resuming normal operations
[Mon Mar 25 01:29:21.559116 2024] [core:notice] [pid 24018:tid 139864408975232] AH00094: Command line: '/usr/sbin/apache2'
[Mon Mar 25 01:37:03.786944 2024] [mpm_event:notice] [pid 24018:tid 139864408975232] AH00492: caught SIGWINCH, shutting down gracefully
[Mon Mar 25 01:37:03.846721 2024] [mpm_event:notice] [pid 24171:tid 140244488513408] AH00489: Apache/2.4.52 (Ubuntu) configured -- resuming normal operations
[Mon Mar 25 01:37:03.848395 2024] [core:notice] [pid 24171:tid 140244488513408] AH00094: Command line: '/usr/sbin/apache2'
root@srv497201:/# ls -l /etc/apache2/sites-enabled
total 0
lrwxrwxrwx 1 root root 35 Mar 23 19:06 000-default.conf -> ../sites-available/000-default.conf
lrwxrwxrwx 1 root root 34 Mar 25 01:28 ourbrandtv.conf -> ../sites-available/ourbrandtv.conf
\\\\\\\\\\\\//////////////////////////////////////////////////////////////







i! I'm here to answer your questions. How can I help you?

6:52 AM
i want to add laravel app with db for testing purpose
6:52 AM
profile
Sure, to set up a Laravel app with a database on your VPS, you can follow these general steps:

Install PHP and Composer:
Update your package list:
Copy
sudo apt update
Install PHP and required extensions:
Copy
sudo apt install php php-cli php-mbstring unzip
Install Composer:
Copy
sudo php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
     sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
     sudo php -r "unlink('composer-setup.php');"
Install and configure MySQL:
Install MySQL server:
Copy
sudo apt install mysql-server
Secure the installation and set a password for the root user:
Copy
sudo mysql_secure_installation
Create a new database and user for your Laravel app:
Log in to MySQL:
Copy
sudo mysql
Create a new database and user:
Copy
CREATE DATABASE laravel_db;
     CREATE USER 'laravel_user'@'localhost' IDENTIFIED BY 'your_password';
     GRANT ALL ON laravel_db.* TO 'laravel_user'@'localhost';
     FLUSH PRIVILEGES;
Install Laravel:
Navigate to your web directory:
Copy
cd /var/www/html
Install Laravel using Composer:
Copy
composer create-project --prefer-dist laravel/laravel your_project_name
Configure Laravel to use the database:
Update the database connection details in the .env file within your Laravel project directory:
Copy
DB_CONNECTION=mysql
     DB_HOST=127.0.0.1
     DB_PORT=3306
     DB_DATABASE=laravel_db
     DB_USERNAME=laravel_user
     DB_PASSWORD=your_password
Set up your web server to serve the Laravel app:
If you're using Apache, create a new virtual host configuration file for your Laravel app. If you're using Nginx, configure a new server block.
Set appropriate file permissions:
Ensure that your web server has the necessary permissions to read and write to the Laravel project directories.
Test your Laravel app:
Access your Laravel app through a web browser and verify that it's working correctly.
Remember to replace laravel_db, laravel_user, and your_password with the actual database name, username, and password you want to use.

If you encounter any issues or need further assistance with any of these steps, feel free to ask!

///////////////////////////////////////////////////////////////////////





root@srv497201:/var/www/ourbrandtv# root@srv497201:/var/www/ourbrandtv# ls
//
