# Contao 4 - Installation
###### by Moritz Petzka [petzka.com](https://petzka.com) 

<br>

##### 1. generate directory for Contao installation (e.g. `my-contao/`)
##### 2. generate `web/` directory inside Contao installation path (`my-contao/`)
##### 3. set `my-contao/web/` as website root in the server settings
##### 4. Download [contao-manager.phar](https://contao.org/de/download.html) and drop the file in `my-contao/web/`
##### 6. Rename `contao-manager.phar` to `contao-manager.phar.php`
##### 7. Open URL `[your domain]/contao-manager.phar.php` in browser to run the installation


#### Next Steps

##### [Install Contao Theme](../theme_installation/README.md)
##### [Add Custom Bundles](../bundle_installation/README.md)
##### [Troubleshooting](../troubleshooting/README.md)

<br>

## Configuration For Local Use
### XAMPP (Windows 10):

##### PHP configuration
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

#### Add Virtual Host
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

##### [Overwiev](../..//README.md)

