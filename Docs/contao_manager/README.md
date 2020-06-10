# Contao 4 - Contao Manager
###### by Moritz Petzka [petzka.com](https://petzka.com)
 
<br>

## Download Contao Manager


## Install Contao Manager



## Enter Contao Manager
Type URL `<your domain>/contao-manager.phar.php` in your Browser and enter login credentials to launch Contao Manager

<div style="width: 72px">

![contao_manager_home](../screenshots/contao_manager_home.jpg | width=270px ){ }


## Update Bundle 


   


##### Go to "PACKAGES"
##### Click on "Update" on Bundle you want update
##### Click on "Apply Changes"


##### Run composer update

```bash
php composer.phar update
```

##### Enter SSH server
```bash
ssh -p 22 -t username@your-domain "cd public_html/www; exec \$SHELL -l"
```
replace: `22` with port number, <br>
`username@your-domain` with your credentials <br>
and: `public_html/www` with path to your contao installation


##### Run composer update

```bash
php composer.phar update
```


<br>


##### [Troubleshooting](../troubleshooting/README.md)
##### [Overwiev](../..//README.md)

