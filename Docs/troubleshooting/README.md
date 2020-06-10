# Contao 4 - Troubleshooting
#### by Moritz Petzka [petzka.com](https://petzka.com) 

<br>

## Contao CMS

<details>
    <summary>
        reset admin password
    </summary>

Change admin user password with phpMyAdmin:
• login to phpMyAdmin and select the right database<br>
• search for table `tl_user`<br>
• search for the admin user<br>
• generate new encrypted password with [https://bcrypt-generator](https://bcrypt-generator.com/) <br>
• fill encrypted password to password field in database and save<br>
• now you can go to Contao backend and login with the new password<br>

</details>


<details>
    <summary>
        Contao-Installtool blocked
    </summary>

set `installCount` in `TL_CONFIG` to 0:
```bash
$GLOBALS['TL_CONFIG']['installCount'] = 0;
```
File: `system/config/localconfig.php`

</details>



<br>

## SSH `composer.phar`

<details>
    <summary>
        memory_limit issue
    </summary>

To get the current memory_limit value, run:
```bash
php -r "echo ini_get('memory_limit').PHP_EOL;"
```

Use -1 for unlimited: 
```bash
php -d memory_limit=-1 composer.phar <...>
```
</details>


