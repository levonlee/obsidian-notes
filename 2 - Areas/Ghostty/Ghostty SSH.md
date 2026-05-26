Old remote servers might not recognize Ghostty's term: xterm-ghostty
When ssh to these remote servers, the delete key entered becomes a space

## Option 1: Change the term and then ssh in as xterm-256color
`TERM=xterm-256color ssh user@remote-host`

## Option 2: Teach the remote server how to deal with Ghostty's term: xterm-ghostty

First, commented these 2 in local `~/.ssh/config`
```
# RemoteCommand sudo su -
# RequestTTY yes
```

This is supposed to work but it doesn't for me: `ghostty +ssh-terminfo myserver`

We do it manually. This will create
`ls -ld /home/ubuntu/.terminfo/* /home/ubuntu/.terminfo/*/*`

```
/home/ubuntu/.terminfo/g
/home/ubuntu/.terminfo/g/ghostty -> ../x/xterm-ghostty
/home/ubuntu/.terminfo/x
/home/ubuntu/.terminfo/x/xterm-ghostty
```

`infocmp -x | ssh myserver 'mkdir -p ~/.terminfo && tic -x -o ~/.terminfo /dev/stdin'`

Then we uncomment RemoteCommand and RequestTTY, ssh in as root, and link the `.terminfo`
`mkdir -p /root/.terminfo && ln -snf /home/ubuntu/.terminfo/x /root/.terminfo/x`
