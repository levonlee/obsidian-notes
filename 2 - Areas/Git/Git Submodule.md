```sh
git submodule status
# -ca123e90e1b500a3f805b80ec3cd40c7515df7f1 devdocker
```

It has a prefix `-` meaning the submodule is not initialized. Inside the repo, initialize it: `git submodule update --init --recursive`

```sh
git submodule update --init --recursive
# Submodule 'devdocker' (git@my.code.com:devops/devdocker.git) registered for path 'devdocker'
# Cloning into '/Users/lili/devdocker'...
# Submodule path 'devdocker': checked out 'ca123e90e1b500a3f805b80ec3cd40c7515df7f1'
```

```sh
git submodule status
# ca123e90e1b500a3f805b80ec3cd40c7515df7f1 devdocker (heads/master)
```

No more prefix meaning the submodule is up to date. If later on there's a `+` prefix, it means you have to do this after `git pull`: `git submodule update`

## Submodule with branch specified
`cat .gitmodules`
```
[submodule "localdev"]
        path = devdocker
        url = git@me.com:devops/localdev.git
[submodule "e2e"]
        path = e2e
        url = git@me.com:devops/playwright.git
        branch = main
```

If the playwright repo (from .gitmodules we know it is pointing to the tip of branch `main`) has a new commit in `main` and you want to update the current repo to point to the HEAD:
```sh
git submodule update --remote e2e
git add e2e && git commit
```

For `localdev` submodule that doesn't have the branch specified:
```sh
cd devdocker
git checkout master
git pull
git status
# Check the commit hash
git log -1
cd ..
git add devdocker
# Check the commit hash again
git submodule status devdocker
```