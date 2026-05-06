```sh
nginx -T 2>/dev/null | grep -nE "fastcgi_ignore_client_abort|fastcgi_read_timeout|fastcgi_send_timeout"
```

