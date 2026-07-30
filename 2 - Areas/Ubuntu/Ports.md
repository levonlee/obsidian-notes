## Ports a PID is Listening

### Linux

```sh
ss -lntup | grep 'pid=8033'
```

Options:
- `l`: listening only
- `n`: numeric (no DNS/service-name lookups)
- `t/u`: TCP/UDP
- `p`: show process. Needs root to see PIDs for processes you don't own.

### macOS
```sh
lsof -nP -i -a -p 8033
```
