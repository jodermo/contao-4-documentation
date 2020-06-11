# Contao 4 - SSH & Composer Usement

<br>

## SSH
Enter SSH server
```bash
ssh -p 22 -t username@your-domain "cd public_html/www; exec \$SHELL -l"
```
replace: `22` with port number, <br>
`username@your-domain` with your credentials <br>
and: `public_html/www` with path to your contao installation<br>

(add `-vvv` to log output)
## SSH & XAMPP

SSH on localhost (`XAMPP default SSL port is 443`)
```
ssh -p 443 root@127.0.0.1
```

SSH on local virtual host (`contao-demo`)
```
ssh -p 443 root@contao-demo
```


<br>

<br>

## Update `composer.phar`
default 
```bash
php composer.phar update
```
watch output in terminal `-vvv`
```bash
php composer.phar update -vvv
```
unlimited memory `memory_limit=-1`
```bash
php -d memory_limit=-1 composer.phar update
```
all together
```bash
php -d memory_limit=-1 composer.phar update -vvv
```
<br>

## Clear Cache `composer.phar`

```bash
php composer.phar clearcache
```
<br>

## Clear Contao Cache
development cache
```bash
vendor/bin/contao-console cache:clear --env=dev
```
production cache
```bash
vendor/bin/contao-console cache:clear --env=prod
```

<br>

#### • [Documentation Overwiev](../..//README.md)
#### • [Troubleshooting](../troubleshooting/README.md)

######  © 2020 by Moritz Petzka [petzka.com](https://petzka.com) 

