502/504 can only be produced before the response starts.

So a truncated response with code 200 is possible.

Nginx `fastcgi_read_timeout` is not a total-request limit, it's the maximum gap between 2 successive reads from PHP-FPM. If it's not set, by default is 60 seconds.

```sh
nginx -T 2>/dev/null | awk '/^# configuration file/{f=$4} /fastcgi_read_timeout|proxy_read_timeout/{print f, $0}'
```

