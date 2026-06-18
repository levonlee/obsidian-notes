Without changing the `Lock Screen` setting, keep the computer running:
```sh
# You need to manually Ctrl+c to stop
caffeinate -i

# Keep active for 14400 seconds = 4 hours
caffeinate -i -t 14400
```