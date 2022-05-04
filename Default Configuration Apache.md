**CentOS**

~]# vi /etc/httpd/conf.d/vhost.conf
```
<VirtualHost *:80>
    DocumentRoot /var/www/html
    ServerName www.domain.name
</VirtualHost>

#Domain Baru
<VirtualHost *:80>
    DocumentRoot /var/www/virtual.host
    ServerName www.domain.name
    ServerAdmin webmaster@domain.name
    ErrorLog logs/domain.name-error_log
    CustomLog logs/domain.name-access_log combined
</VirtualHost>
```

~]# mkdir /var/www/virtual.host
~]# systemctl restart httpd
