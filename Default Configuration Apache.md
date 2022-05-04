**CentOS**

Create New file vhost.co
~]# vi /etc/httpd/conf.d/vhost.conf
# settings for original domain
<VirtualHost *:80>
    DocumentRoot /var/www/html
    ServerName www.srv.world
</VirtualHost>

# settings for new domain
<VirtualHost *:80>
    DocumentRoot /var/www/virtual.host
    ServerName www.virtual.host
    ServerAdmin webmaster@virtual.host
    ErrorLog logs/virtual.host-error_log
    CustomLog logs/virtual.host-access_log combined
</VirtualHost>

<Directory "/var/www/virtual.host">
    Options FollowSymLinks
    AllowOverride All
</Directory>

[root@www ~]# mkdir /var/www/virtual.host
[root@www ~]# chmod 755 /var/www/virtual.host
[root@www ~]# systemctl restart httpd
