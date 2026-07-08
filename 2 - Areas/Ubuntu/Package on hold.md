A package on hold is pinned so normal APT operations will not upgrade, install, remove, or downgrade it automatically. This matters before an OS/MySQL upgrade because a held package can silently prevent the upgrade from replacing something important.
  
```sh
apt-mark showhold
```