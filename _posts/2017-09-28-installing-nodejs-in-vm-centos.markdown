---
layout: post
title:  "Installing Node.js in CentOS"
date:   2017-09-28 09:00:00 +1000
categories: digitalmarketing
url: installing-nodejs-in-centos
---

> The purpose of this documentation is to help with managing the version of Node.js and NPM in a CentOS.

## Lets begin

Firstly I read this to get an understanding and what I need to remove within the CentOS VM: <a href="https://hungred.com/how-to/completely-removing-nodejs-npm/" target="blank">Completely removing nodejs npm</a>

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

<a href="https://github.com/creationix/nvm/blob/master/README.md" target="blank">Download nvm</a>

Good article on <a href="https://davidwalsh.name/nvm" target="blank">managing Node.js versions with nvm</a>. Read about <a href="https://github.com/creationix/nvm/blob/master/README.md#usage" target="blank">nvm usage</a> and if you need information about <a href="https://nodejs.org/en/download/releases/" target="blank">version releases of Node.js</a>.

```
nvm install 7.0.0
```

```
nvm use --delete-prefix v7.0.0
```

```
node -v
```

```
npm -v
```

You should now have Node.js running with an updated version and npm installed. Go ahead and install all other things like bower, grunt or whatever your development environment consists of.
