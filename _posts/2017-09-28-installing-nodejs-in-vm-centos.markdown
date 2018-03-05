---
layout: post
title:  "Installing Node.js in CentOS"
date:   2017-09-28 09:00:00 +1000
categories: nodejs
url: installing-nodejs-in-centos
---

<blockquote class="blockquote">
The purpose of this documentation is to help with managing the version of Node.js and NPM in a CentOS.
</blockquote>

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

We found that we had to play around with the version of certain npm packages. The command below helped with identifying the npm package installed.

```
npm list nameofpackage
```

## Conclusion

We can update all the npm packages below except for grunt-contrib-imagemin. The compression libraries it was using are not supported in CentOS version 5. These libraries would have to be updated.

An interim solution of using grunt-image instead of grunt-contrib-imagemin was implemented. We came across one problem with grunt-image which was to do with <a href="https://github.com/gruntjs/grunt-contrib-copy/issues/21">open file limits</a>. Setting the open file limit of our VM's higher helped the task run without any problems. However it was only an issue due to trying to compress 933 images. If we abstract out tasks to specific tasks it'll run faster. 

```
ulimit -n 10480
```

<blockquote class="blockquote">Running Node.js version 7.0.0 with npm version 3.10.8</blockquote>

Package.json

```
{
    "name": "Anonymous",
    "version": "2.0.0",
    "description": "Anonymous",
    "author": "Anonymous",
    "devDependencies": {
    "grunt": "1.0.1",
    "grunt-contrib-sass": "1.0.0",
    "grunt-contrib-uglify": "3.1.0",
    "grunt-contrib-watch": "1.0.0",
    "grunt-image": "3.0.0",
    "grunt-newer": "1.3.0",
    "load-grunt-tasks": "3.5.2",
    "lodash": "4.17.4",
    "time-grunt": "1.4.0"
    }
}
```
