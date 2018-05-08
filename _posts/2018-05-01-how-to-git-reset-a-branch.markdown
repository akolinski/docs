---
layout: post
title:  "RVM, Linuxbrew, Node NPM, Grunt"
date:   2018-05-08 09:00:00 +1000
categories: git
url: rvm-linuxbrew,node-npm-grunt
---

<blockquote class="blockquote">
    Set up software on a CentOS machine so we can run Grunt.
</blockquote>

## Lets begin

If you are using vagrant.

```
vagrant ssh
```

Lets install <a target="_blank" href="https://rvm.io/rvm/install" target="blank">RVM</a> first. You may come across some problems. Follow the documentation closely and terminal prompts.

Then install <a target="_blank" href="http://linuxbrew.sh/">linuxbrew</a>. It's a fork of homebrew, a package manager for Linux.

<div class="alert alert-warning">
    <h4 class="alert-heading mt-2 mb-3"><i class="fas fa-info-circle mr-2"></i> Important information to read :P</h4>
    <p class="mb-0">Once installion is successful, in terminal it'll outline 'Next steps' which you have to follow to include brew in your PATH.</p>
</div>

This next step will only work once the above is done correctly. Then to <a target="_blank" href="https://nodejs.org/en/download/package-manager/#macos">install node via a package manager</a>.

```
brew install node
```

Then check if all is good.


```
node -v
```

```
npm -v
```

Now lets install <a target="_blank" href="https://gruntjs.com/getting-started">Grunt</a>.

```
npm install -g grunt-cli
```

Let's now get our package.json file with all our node_modules to install the packages we need to start developing.

```
npm install
```

You're all done!

## Troubleshooting

When running grunt sass:task it returns:

<a href="https://github.com/gruntjs/grunt-contrib-sass/issues/229" target="_blank">You need to have Ruby and Sass installed and in your PATH for this task to work.</a>

Fix:  ```gem install sass```

You need to have the sass gem installed.
