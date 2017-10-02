---
layout: post
title:  "Installing Node.js in CentOS"
date:   2017-09-28 09:00:00 +1000
categories: nodejs
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

## More node more problems

Version of installed npm packages:

```
npm list nameofpackage
```

Had a few problems with the grunt-contrib-imagemin version. Had to make sure that grunt-contrib-imagemin had other plugins installed. Then we had another issue with the globbing pattern not understanding something. https://github.com/gruntjs/grunt-contrib-imagemin/issues/208 jpg,png,jpeg,gif,ico,svg. Installing different version of grunt-contrib-imagemin helps to fix the problem. https://github.com/gruntjs/grunt-contrib-imagemin/issues/372

## Conclusion

We found that installing the latest or later versions of node in CentOS 5.9 isn't supported. If we install a newer version of node js and install all the latest node modules they turn out not to be supported by the library binaries provided in that version of CentOS.

> Running Node.js version 7.0.0 with npm version 3.10.8

Package.json

```
{
  "name": "Anonymous",
  "version": "2.0.0",
  "description": "Anonymous",
  "author": "Anonymous",
  "devDependencies": {
    "grunt": "1.0.0",
    "grunt-contrib-imagemin": "1.0.0",
    "grunt-contrib-sass": "1.0.0",
    "grunt-contrib-uglify": "3.1.0",
    "grunt-contrib-watch": "1.0.0",
    "grunt-newer": "1.3.0",
    "load-grunt-tasks": "3.5.2",
    "lodash": "4.17.4",
    "time-grunt": "1.4.0"
  },
  "dependencies": {
    "imagemin": "5.3.1",
    "imagemin-jpegtran": "5.0.2",
    "imagemin-mozjpeg": "5.1.0",
    "imagemin-pngquant": "5.0.1"
  }
}
```
