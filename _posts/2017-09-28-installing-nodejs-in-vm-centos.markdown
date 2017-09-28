---
layout: post
title:  "Installing Node.js in VM centOS"
date:   2017-09-28 09:00:00 +1000
categories: digitalmarketing
url: installing-nodejs-in-vm-centos
---

> The purpose of this documentation is to help with managing the version of Node.js and NPM in a centos VM.

## Lets begin

Firstly I used this to get an understanding and what I need to remove within the VM: [Completely removing nodejs npm].

```
cd /usr/local/lib/node_modules
```

```
sudo rm -rf npm
```

```
cd /usr/local/lib/node_modules
```

```
sudo rm -rf npm
```

Check your Home directory for any "local" or "lib" or "include" folders, and delete any "node" or "node_modules" from there.

Go to /usr/local/bin and delete any node executable.

Then download nvm and follow the instructions to install node. The latest versions of node come with npm, I believe, but you can also reinstall that as well.

## Download nvm

[managing Node.js versions with nvm]

nvm install 7.0.0

nvm use --delete-prefix v7.0.0

node -v

npm -v

Read about [nvm usage]

## Reading

[Completely removing nodejs npm]
[download nvm]
[managing Node.js versions with nvm]
[Releases of Node.js]

[Completely removing nodejs npm]: https://hungred.com/how-to/completely-removing-nodejs-npm/
[download nvm]: https://github.com/creationix/nvm/blob/master/README.md
[nvm usage]: https://github.com/creationix/nvm/blob/master/README.md#usage
[managing Node.js versions with nvm]: https://davidwalsh.name/nvm
[Releases of Node.js]: https://nodejs.org/en/download/releases/
