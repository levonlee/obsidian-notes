## Enable it on Claude Code Terminal
In a terminal session: `/config`, enable `Enable Remote Control for all sessions`, then all new sessions spawned on this computer's Claude Code terminal will be available to be remote controlled by any desktop or mobile Claude.app.

## Server mode
Create a server mode for a local directory so that other computers/cellphones can create new sessions from desktop/mobile Claude.app and those sessions will run on the local computer.

On the local computer run:
```sh
tmux new -s rc
cd /Users/lili/myrepo
while true; do caffeinate -i claude remote-control --name "myrepo (home)"; sleep 5; done
# ctrl-b d to detach
# ctrl-c twice to stop this
```




