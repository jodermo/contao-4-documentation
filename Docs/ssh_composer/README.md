# Contao 4 - SSH & Composer
###### by Moritz Petzka [petzka.com](https://petzka.com) 

<br>

## SSH

##### Development Version [digitale-schule.petzka.com](http://digitale-schule.petzka.com):
```bash
ssh -p 222 -t petzka@petzka.com "cd public_html/digitale-schule; exec \$SHELL -l"
```

##### Production Version [no-domeain-yet](#):

```bash
ssh -p 22 -t username@no-domeain-yet "cd public_html/www; exec \$SHELL -l"
```

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
