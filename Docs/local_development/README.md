# Contao 4 - Local Development

<br>

## Windows & Coposer
"The installer will download composer for you and set up your PATH environment variable so you can simply call composer from any directory. <br>
Download and run [Composer-Setup.exe](https://getcomposer.org/Composer-Setup.exe) - it will install the latest composer version whenever it is executed." <br>
###### Website & Download: [https://getcomposer.org/](https://getcomposer.org/download/) 

<br>

## Local Server (width XAMPP)

#### For Windows, I recommend XAMPP!
Contao has preconfiguration for XAMPP that worked very well for me. 

"XAMPP is a completely free, easy to install Apache distribution containing MariaDB, PHP, and Perl. The XAMPP open source package has been set up to be incredibly easy to install and to use."

###### Website & Download: [www.apachefriends.org](https://www.apachefriends.org/index.html)

<br>


### XAMPP configuration for Contao 4
###### ! Note: In this example, the XAMPP install path is `c:\xampp\`

#### PHP Configuration
php.ini `c:\xampp\php\php.ini`
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

#### Virtual Host

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

### XAMPP & SSH

Open XAMPP Shell, type `php -m` to check if `ssh` module is already running.


#### Activate SSH in XAMPP:

First you need `php_ssh2.dll` in your XAMPP installation <br>
Look for `c:\xampp\php\ext\php_ssh2.dll`.

If not, you can download `php_ssh2.dll` here: [phpfashion.com/php-ssh2-dll-for-php-5-6-7-4]( https://phpfashion.com/php-ssh2-dll-for-php-5-6-7-4) <br>
Pay attention to the right XAMPP installation (32bit or 64bit) and the installed PHP version.

Add following line to `c:\xampp\php\php.ini`
```
extension=ssh2
```
Then stop and start Apache,  open XAMPP Shell and type `php -m` to check if `ssh` module is now listed.

<br>

### XAMP, SSH & Virtual Host
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


