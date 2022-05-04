# **Ubuntu**
----

* Create and Go to file **domain.name.conf**.
```
vi /etc/apache2/sites-available/domain.name.conf
```
* Default Configuration.
```
#create new
<VirtualHost *:80>
    ServerName www.domain.name
    ServerAdmin webmaster@domain.name
    DocumentRoot /home/ubuntu/public_html
    ErrorLog /var/log/apache2/domain.name.error.log
    CustomLog /var/log/apache2/domain.name.access.log combined
    LogLevel warn
</VirtualHost>
```
* Activating VirtualHost File and Restart service Apache.
```
a2ensite domain.name
systemctl restart apache2
```
