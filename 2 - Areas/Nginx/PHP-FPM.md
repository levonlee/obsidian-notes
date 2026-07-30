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

## Search multiple configs across the master and pool overrides:

```sh
grep -rn -E 'max_execution_time|max_input_time|request_terminate_timeout|default_socket_timeout' \ > /etc/php* /etc/php-fpm* 2>/dev/null | grep -v '^\s*;'
```

Result
```
/etc/php/7.4/cli/phpini.bak:116:; max_input_time
/etc/php/7.4/cli/phpini.bak:388:max_execution_time = 30
/etc/php/7.4/cli/phpini.bak:398:max_input_time = 60
/etc/php/7.4/cli/phpini.bak:874:default_socket_timeout = 60
/etc/php/7.4/cli/php.ini:121:; max_input_time
/etc/php/7.4/cli/php.ini:380:max_execution_time = 30
/etc/php/7.4/cli/php.ini:390:max_input_time = 60
/etc/php/7.4/cli/php.ini:869:default_socket_timeout = 60
/etc/php/7.4/apache2/php.ini:116:; max_input_time
/etc/php/7.4/apache2/php.ini:388:max_execution_time = 30
/etc/php/7.4/apache2/php.ini:398:max_input_time = 60
/etc/php/7.4/apache2/php.ini:874:default_socket_timeout = 60
/etc/php/7.4/fpm/php.ini:116:; max_input_time
/etc/php/7.4/fpm/php.ini:388:max_execution_time = 120
/etc/php/7.4/fpm/php.ini:398:max_input_time = 60
/etc/php/7.4/fpm/php.ini:874:default_socket_timeout = 60
/etc/php/7.4/fpm/pool.d/www.conf:338:; be killed. This option should be used when the 'max_execution_time' ini option
/etc/php/7.4/fpm/pool.d/www.conf:342:;request_terminate_timeout = 58s
/etc/php/7.4/fpm/pool.d/www.conf:344:; The timeout set by 'request_terminate_timeout' ini option is not engaged after
/etc/php/7.4/fpm/pool.d/www.conf:350:;request_terminate_timeout_track_finished = no
```

## Timeout
`request_terminate_timeout`: kills the worker mid-request. Output already flushed reaches the browser; the rest never comes. No error on the page by design. Default is 0.
`max_execution_time`: PHP fatals, but with display_errors = Off on prod the message goes to the error log instead of the page. It does not count time blocked on MySQL queries or socket reads on Linux — only CPU time in PHP itself. 
`fastcgi_read_timeout / send_timeout (nginx)`: normally a 504 page, but if headers and part of the body were already sent, nginx can't replace the response, so you just get a cut-off body.