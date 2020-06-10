# Contao 4 - SSH & Composer
###### by Moritz Petzka [petzka.com](https://petzka.com) 

<br>

## SSH
Enter SSH server
```bash
ssh -p 22 -t username@your-domain "cd public_html/www; exec \$SHELL -l"
```
replace: `22` with port number, <br>
`username@your-domain` with your credentials <br>
and: `public_html/www` with path to your contao installation

<br>

## update `composer.phar`
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

## clear cache `composer.phar`

```bash
php composer.phar clearcache
```
<br>

## clear contao cache
development cache
```bash
vendor/bin/contao-console cache:clear --env=dev
```
production cache
```bash
vendor/bin/contao-console cache:clear --env=prod
```

<br>

##### [Troubleshooting](../troubleshooting/README.md)
##### [Overwiev](../..//README.md)
