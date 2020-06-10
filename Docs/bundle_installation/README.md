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


##### [Troubleshooting](../troubleshooting/README.md)


