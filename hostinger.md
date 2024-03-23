Root password :v5CY5Z+@   abcABC@123 
ssh root@93.188.165.172
exit
scp -P 22 site.zip root@93.188.165.172:/var/www
cd /var/www

unzip site.zip
rm -r site.zip

cd\
ctrl X
systemctl list-units --type=service

press q for quite

systemctl list-units --type=service --state=active

systemctl status your_apache_service_name

install apache:::::::

sudo apt install apache2
sudo netstat -tuln | grep 80
sudo systemctl stop nginx
sudo systemctl start apache2
sudo systemctl status apache2

nano /etc/apache2/sites-available/your-site.conf
<VirtualHost *:80>
       ServerAdmin webmaster@your-site.com
       ServerName your-site.com
       ServerAlias www.your-site.com
       DocumentRoot /var/www/your-site
       ErrorLog ${APACHE_LOG_DIR}/error.log
       CustomLog ${APACHE_LOG_DIR}/access.log combined
   </VirtualHost>
