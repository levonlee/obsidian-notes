## Install and Upgrade
https://docs.astral.sh/uv/getting-started/installation/

```sh
curl -LsSf https://astral.sh/uv/install.sh | sh
uv self update
uv --version
```

## Install a Different Version of Python
See a list of Pythons that are installed and can be installed
```sh
uv python list
```

Do NOT remove the macOS installed Python:
```
cpython-3.9.6-macos-aarch64-none                     /usr/bin/python3
```

User installed Python looks like this:
Old:
```
cpython-3.13.12-macos-aarch64-none                   /Users/lili/.local/share/uv/python/cpython-3.13-macos-aarch64-none/bin/python3.13
```
Now: This allows directly running `python3.14 --version`
```
cpython-3.14.7-macos-aarch64-none                    /Users/lili/.local/bin/python3.14 -> /Users/lili/.local/share/uv/python/cpython-3.14-macos-aarch64-none/bin/python3.14
```

See details about each version of Python: https://www.python.org/downloads/

Install a version: `uv python install 3.14`

You should always update to the latest patch release of a deliberately chosen, supported Python minor version:
```
3.14.7
│ │  └─ patch release: bug and security fixes
│ └──── minor/feature release: new features and possible compatibility changes
└────── major version
```

```sh
uv python upgrade 3.13
```

Pin a version on a project (directory): `cd ~/myproject && uv python pin 3.13 && uv run python --version`, then a file is created: `~/myproject/.python-version`
```
Python 3.13.12
```

After pinning, in the directory running `uv run python your_script.py` will use `Python 3.13.12`

Use a specific Python version for a newly installed tool (isolated tool environment): `uv tool install --python 3.13 graphifyy` You can also use this to update the Python version

Or you can upgrade the tool and change the Python version: `uv tool upgrade --python 3.14 graphifyy`

Check the Python version for an installed tool:
```
➜  ~/myproject uv tool list --show-paths
graphifyy v0.9.34 (/Users/lili/.local/share/uv/tools/graphifyy)
- graphify (/Users/lili/.local/bin/graphify)
- graphify-mcp (/Users/lili/.local/bin/graphify-mcp)
➜  ~/myproject uv tool dir
/Users/lili/.local/share/uv/tools
➜  ~/myproject "$(uv tool dir)/graphifyy/bin/python" --version
Python 3.14.7
```

## 

