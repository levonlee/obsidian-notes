Without checking out remote branch `abc` (changing the local branch pointer), create a local branch that is `origin/abc`.

```sh
git fetch
git branch --track abc origin/abc
```

If later, the remote branch has advanced, and fast-forward can update the local branch:
```sh
git fetch
git fetch origin abc:abc
```

You can do forced fetch if fast-forward is not possible:
```sh
git fetch origin +abc:abc
# or the long form: git fetch origin +refs/heads/abc:refs/heads/abc
```
