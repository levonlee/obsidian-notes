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