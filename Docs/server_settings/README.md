# Contao 4 - Web Server Requirements

• PHP 7.2+ with GDlib, DOM and Phar <br>
• MySQL 5.5.7+ <br>
• InnoDB with innodb_large_prefix enabled

##### php.ini
    memory_limit = 256M
    max_execution_time = 30
    file_uploads = On
    upload_max_filesize = 32M
    post_max_size = 32M
    max_input_vars = 1000
    opcache.enable = 1
    opcache.enable_cli = 0
    opcache.max_accelerated_files = 16000
    safe_mode = Off
    open_basedir = NULL

<br>

##### MySQL
    innodb_large_prefix = 1
    innodb_file_format = Barracuda
    innodb_file_per_table = 1
utf8mb4

#### `config/config.yml`

```yaml
doctrine:
    dbal:
        connections:
            default:
                default_table_options:
                    charset: utf8
                    collate: utf8_unicode_ci
                    engine: MyISAM
```

<br>

#### • [Documentation Overwiev](../..//README.md)
#### • [Troubleshooting](../troubleshooting/README.md)

######  © 2020 by Moritz Petzka [petzka.com](https://petzka.com) 


