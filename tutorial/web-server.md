# Apache HTTP Configurations
```
/home/sa/apache/ 
+-- httpd-vhosts.conf (linked to /etc/apache2/site-available/000-my-httpd-vhosts.conf) 
+-- httpd-ssl.conf (linked to /etc/apache2/site-available/001-my-httpd-ssl.conf)
+-- conf
|   +-- conf.d 
|   |   +-- *.conf (included in ./../httpd-vhosts.conf)
|   +-- include-vhost-80 
|   |   +-- *.conf (included in ./../httpd-vhosts.conf <VirtualHost :80>)
|   +-- include-vhost-443
|   |   +-- *.conf (included in ./../httpd-vhosts.conf <VirtualHost :443>)
+-- scripts
|   +-- reload-httpd.sh (convenient script for reloading Apache HTTP Service)
|   +-- map-local-tomcat.sh (create proxies for localhost Apache Tomcat)
|   +-- enable-mods.sh (not completed)

```
