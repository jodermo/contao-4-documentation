# Contao 4 - Configuration



## Contao Root Page

The alias of start (root) page has to be `index`

<br>

## Remove `.html` suffix from URLs

Add following code to `config/config.yml`:
```yaml
contao:
    url_suffix: "/"
```

Add following code to `web/.htaccess`:
```yaml
# Rewrite all .html --> /
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule (.*)\.html$ %{ENV:BASE}/$1/ [L,R=301]

# add trailing slash
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{THE_REQUEST} !/contao [NC]
RewriteCond %{THE_REQUEST} !/_contao [NC]
RewriteRule ^.*[^/]$ /$0/ [L,R=301]
```
insert after these lines:
```yaml
# If the requested filename exists, simply serve it.
# We only want to let Apache serve files and not directories.
RewriteCond %{REQUEST_FILENAME} -f
RewriteRule ^ - [L]
```

<br>

#### • [Documentation Overwiev](../..//README.md)
#### • [Troubleshooting](../troubleshooting/README.md)

######  © 2020 by Moritz Petzka [petzka.com](https://petzka.com) 


