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
