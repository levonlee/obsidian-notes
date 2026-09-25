## New session
```sh
tmux new -s mysql84
```

## Detach
```sh
Ctrl-b, then d
```

## Exit and kill the current session
Run this from inside the session:
```sh
tmux kill-session
```
This closes the session and terminates programs running in its panes.

## List sessions
```sh
tmux ls
```

## Attach
```sh
tmux attach -t mysql84
```

## Config
To keep more than the default 2,000 lines in Copy Mode, add this to `~/.tmux.conf`:
```tmux
set -g history-limit 50000
```

In tmux 3.0a, the new limit applies only to panes created afterward. To apply it in the current session without restarting tmux, run `tmux set-option history-limit 50000`, then create a new window (`Ctrl-b`, then `c`) or pane. Changing the setting cannot recover lines already discarded from an existing pane. See the [tmux 3.0a manual](https://raw.githubusercontent.com/tmux/tmux/3.0a/tmux.1).
