## Check values of certain configs

Find which php-fpm: `ps -ef | grep -E "php-fpm|php[0-9.]+-fpm" | grep -v grep | head`

```text
  root     1815742       1  0 Feb25 ?        00:03:26 php-fpm: master process (/etc/php/7.4/fpm/php-fpm.conf)
  www-data 2307250 1815742  3 16:45 ?        00:01:03 php-fpm: pool www
  www-data 2312110 1815742  2 16:49 ?        00:00:35 php-fpm: pool www
  www-data 2312148 1815742  3 16:49 ?        00:00:50 php-fpm: pool www
  www-data 2312151 1815742  2 16:49 ?        00:00:39 php-fpm: pool www
  www-data 2312152 1815742  2 16:49 ?        00:00:41 php-fpm: pool www
  www-data 2312153 1815742  1 16:49 ?        00:00:23 php-fpm: pool www
  www-data 2312154 1815742  2 16:49 ?        00:00:39 php-fpm: pool www
  www-data 2312275 1815742  2 16:49 ?        00:00:41 php-fpm: pool www
  www-data 2319476 1815742  1 16:55 ?        00:00:20 php-fpm: pool www
```

`/usr/sbin/php-fpm7.4` is found
Get the config files: `/usr/sbin/php-fpm7.4 -i 2>/dev/null | grep -E "Loaded Configuration File|Scan this dir|Additional \.ini"`
```text
  Loaded Configuration File => /etc/php/7.4/fpm/php.ini
  Scan this dir for additional .ini files => /etc/php/7.4/fpm/conf.d
  Additional .ini files parsed => /etc/php/7.4/fpm/conf.d/10-mysqlnd.ini,
```

Search the configs
```sh
# 1. Main php.ini for the FPM SAPI
sudo grep -nE "^[^;]*ignore_user_abort" /etc/php/7.4/fpm/php.ini

# 2. The conf.d scan dir (any .ini drop-in)
sudo grep -RInE "^[^;]*ignore_user_abort" /etc/php/7.4/fpm/conf.d/

# 3. Pool overrides (php_value / php_admin_value can set per-pool INI)
sudo grep -RInE "ignore_user_abort" /etc/php/7.4/fpm/pool.d/
```
