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

root@srv497201:/var/www/ourbrandtv# root@srv497201:/var/www/ourbrandtv# ls
