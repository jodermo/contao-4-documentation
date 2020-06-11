# Contao 4 - Local Development

<br>

## XAMP

### I recommend XAMPP
##### Contao has preconfiguration for XAMPP that worked very well for me. 

"XAMPP is a completely free, easy to install Apache distribution containing MariaDB, PHP, and Perl. The XAMPP open source package has been set up to be incredibly easy to install and to use."

###### Website & Download: [www.apachefriends.org](https://www.apachefriends.org/index.html)

<br>

###### In this example, the XAMPP install path is `c:\xampp\`

##### XAMPP PHP configuration for Contao 4

change following lines in `c:\xampp\php\php.ini`
```
file_uploads = On
upload_temp_dir = "C:\xamp\tmp"
upload_max_filesize = 256M
allow_url_fopen = On
max_execution_time = 360
memory_limit = -1
post_max_size = 128M
extension=intl
extension=soap
```

<br>

### Add virtual host for Contao project
To make the local Contao project available with custom URL (e.g. `http://contao-demo`) <br>
add following code to `c:\xampp\apache\conf\extra\httpd-vhosts.conf`
```xml
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

## SSH in XAMPP

Open XAMPP Shell, type `php -m` to check if `ssh` module is running

### How to activate SSH in XAMPP:

You need `php_ssh2.dll` in your XAMPP installation (`c:\xampp\php\ext\php_ssh2.dll`)

You can download `php_ssh2.dll` here: [phpfashion.com/php-ssh2-dll-for-php-5-6-7-4]( https://phpfashion.com/php-ssh2-dll-for-php-5-6-7-4) <br>
Pay attention to the right XAMPP installation (32bit or 64bit) and installed PHP version.

Drop `php_ssh2.dll` file to `c:\xampp\php\ext\` <br> and add following line to `c:\xampp\php\php.ini`
```
extension=ssh2
```
Restart Apache and open XAMPP Shell, type `php -m` to check if `ssh` module is running

Remove `#` from following line in `c:\xampp\apache\conf\httpd.conf `
```
#LoadModule ssl_module modules/mod_ssl.so
```
<br>

### Activate Virtual Host for SSH
To make the local Contao project available over SSH (e.g. `root@contao-demo`) <br>
add following code to `c:\xampp\apache\conf\extra\httpd-vhosts.conf`
```xml
<VirtualHost *:443>
    DocumentRoot "<project path>"
    ServerName contao-demo
    SSLEngine on
    SSLCertificateFile "conf/ssl.crt/server.crt"
    SSLCertificateKeyFile "conf/ssl.key/server.key"
</VirtualHost>
```

<br>

### Enter SSH 

SSH on localhost (`XAMPP default SSL port is 443`)
```
ssh -p 443 root@127.0.0.1
```

SSH on Virtual Host (`contao-demo`)
```
ssh -p 443 root@contao-demo
```
(add `-vvv` to log output)

<br>


#### • [Documentation Overwiev](../..//README.md)
#### • [Troubleshooting](../troubleshooting/README.md)

######  © 2020 by Moritz Petzka [petzka.com](https://petzka.com) 


