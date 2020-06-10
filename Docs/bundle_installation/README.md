# Contao 4 - Bundle Installation
###### by Moritz Petzka [petzka.com](https://petzka.com) 

<br>

###### Example Contao/Symfony Bundle: <br> [github.com/jodermo/petzka-demo-bundle](https://github.com/jodermo/petzka-demo-bundle)



## Add Bundle as Git-Repository<br>
add code to \<contao root path\>/composer.json
```json
{
    "repositories": [
        {
            "type": "git",
            "url": "https://github.com/jodermo/petzka-demo-bundle.git"
        }
    ],
    "require": {
        "petzka/demo-bundle": "dev-master"
    },
    "config": {
        "preferred-install": {
            "petzka/*": "source",
            "*": "dist"
        }
    },
}
```

##### ! Note: use version prefix `dev-` as long as there is no stable release, e.g:
    "petzka/demo-bundle": "dev-master"

## Add Bundle as local Repository<br>
add code to \<contao root path\>/composer.json
```json
{
    "...": "...",
    "repositories": [
        {
            "type": "path",
            "url": "repositories/petzka-demo-bundle"
        }
    ],
    "require": {
        "...": "...",
        "petzka/demo-bundle": "dev-master"
    },
    "config": {
        "preferred-install": {
            "petzka/*": "source",
            "*": "dist"
        }
    },
}
```

<br>

## Update Bundle Contao Manager

##### Enter Contao Manager
Type URL `<your domain>/contao-manager.phar.php` in your Browser and enter login Admin credentials to launch Contao Manager

    
   
![contao_manager_home](../screenshots/contao_manager_home.jpg)

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

