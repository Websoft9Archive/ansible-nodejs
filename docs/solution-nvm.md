# Using NVM

[NVM](https://github.com/creationix/nvm), Node Version Manager - Simple bash script to manage multiple active node.js versions

## Why NVM?

Since npm and node.js products are managed by different entities, updates and maintenance can become complex. Also, the Node.js installation process installs npm in a directory that only has local permissions. This can cause permissions errors when you attempt to run packages globally.

To solve both these issues, many developers opt to use a _node version manager_, or _nvm_, to install npm. The version manager will avoid permissions errors, and will solve the complexities of updating Node.js and npm.<br />In addition, developers can use an nvm to test their applications on multiple versions of npm. The nvm enables you to easily switch npm as well as node versions. This makes it easier to ensure that your applications work for most users, even if they are using other versions of npm. If you decide to install a version manager, use the instructions for the version manager you select to learn how to switch versions, and to learn how to keep up-to-date with the latest version of npm.

## Install & Update NVM script

**install** or **update** nvm, you can use the [install script](https://github.com/creationix/nvm/blob/v0.34.0/install.sh) using cURL:

```shell
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.34.0/install.sh | bash
```

or Wget:

```shell
wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.34.0/install.sh | bash
```

`~/.nvm``~/.bash_profile``~/.zshrc``~/.profile``~/.bashrc`

## Uage NVM

To download, compile, and install the latest release of node, do this:

```shell
nvm install node # "node" is an alias for the latest version
```

To install a specific version of node:

```shell
nvm install 6.14.4 # or 10.10.0, 8.9.1, etc
```

The first version installed becomes the default. New shells will start with the default version of node (e.g., `nvm alias default`).

You can list available versions using ls-remote:
```shell
nvm ls-remote
```

And then in any new shell just use the installed version:
```shell
nvm use node
```

Or you can just run it:
```shell
nvm run node --version
```

Or, you can run any arbitrary command in a subshell with the desired version of node:

You can also get the path to the executable to where it was installed:
```shell
nvm which 5.0
```