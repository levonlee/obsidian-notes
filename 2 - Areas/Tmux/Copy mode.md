## Go to copy mode

Tmux by default doesn't use mouse scroll to navigate. Better to go to copy mode and hit arrow keys to page down/page up.

```sh
Ctrl-b [

# to quit
q

# To paste
Ctrl-b ]
```

## Get the key mode
```
tmux show-options -gw mode-keys
```

### emacs
To select:
```sh
# To start
Ctrl-Space

Ctrl-w
```

### vi
```sh
# To start
Space

# To copy
Enter
```