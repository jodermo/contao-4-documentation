# Contao 4 - Local Development

<br>

## Windows

### XAMPP

XAMPP is a completely free, easy to install Apache distribution containing MariaDB, PHP, and Perl. The XAMPP open source package has been set up to be incredibly easy to install and to use.

###### Website & Download: [www.apachefriends.org](https://www.apachefriends.org/index.html)

##### XAMPP PHP configuration for Contao 4
change following lines in php.ini
```
file_uploads = On (ca. Zeile 833)
upload_temp_dir = "C:\xamp\tmp" (ca. Zeile 838)
upload_max_filesize = 256M (ca. Zeile 842)
allow_url_fopen = On (ca. Zeile 853)
max_execution_time = 360 (ca. Zeile 386)
memory_limit = -1 (ca. Zeile 407)
post_max_size = 128M (ca. Zeile 690)
extension=intl (ca. Zeile 917) das Semikolon wegnehmen
extension=soap (ca. Zeile 939) das Semikolon wegnehmen
```

<br>

#### Add virtual host for Contao project
add following code to <b>httpd-vhosts.conf</b><br>
(in \<xampp path\>/apache/conf/extra/)
```
<VirtualHost *:80>
  DocumentRoot "<project path>\web"
  ServerName contao-demo
  <Directory "<project path>\web">
    Options +FollowSymlinks
    AllowOverride All
    Require all granted
  </Directory>

  ErrorLog "D:\xampp\apache\logs\contao-demo_error.log"
  CustomLog "D:\xampp\apache\logs\contao-demo_access.log" combined
</VirtualHost>
```

<br>

#### • [Documentation Overwiev](../..//README.md)
#### • [Troubleshooting](../troubleshooting/README.md)

######  © 2020 by Moritz Petzka [petzka.com](https://petzka.com) 


