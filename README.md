# plenv installer

This tool installs [plenv](https://github.com/tokuhirom/plenv) and friends. It is copied from [pyenv installer](https://github.com/pyenv/pyenv-installer/blob/master/bin/pyenv-installer).

## Prerequisites

### Installation / Update / Uninstallation

Once prerequisites have been installed correctly:

Install:

```shell
$ curl -L https://github.com/gingerhot/plenv-installer/raw/master/bin/plenv-installer | bash
```
Restart your shell so the path changes take effect:

```bash
$ exec $SHELL
```

You can now begin using plenv.

If you need, export USE_GIT_URI to use git:// instead of https:// for git clone.

Update:

see [here](https://github.com/tokuhirom/plenv#upgrading).

Uninstall:

plenv is installed within $PLENV_ROOT (default: ~/.plenv). To uninstall, just remove it:

```shell
$ rm -fr ~/.plenv
```

then remove these two lines from .bashrc:

export PATH="$HOME/.plenv/bin:$PATH"
eval "$(plenv init -)"

and finally, restart your shell:

```shell
$ exec $SHELL
```

Using plenv-installer on Travis CI
Travis itself uses plenv and therefore PLENV_ROOT is set already. To make it work anyway the installation for plenv-installer needs to look like this:

[...]
- unset PLENV_ROOT
- curl -L https://github.com/gingerhot/plenv-installer/raw/master/bin/plenv-installer | bash
- export PATH="$HOME/.plenv/bin:$PATH"
- plenv install 5.18.0
