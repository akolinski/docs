---
layout: post
title:  "How to set up a Vue.js project"
date:   2019-02-15 09:00:00 +1000
categories: git
url: how-to-set-up-a-vue-js-project
---

<blockquote class="blockquote">
    Lets get a Vue.js project up and running, you know so we can bake up some awesome websites.
</blockquote>

# Lets begin

Before we start let's update our node.js version. <a href="https://nodejs.org/en/" target="blank">Install the one "Recommeneded For Most Users"</a>.

Install or Update your NPM version

```
npm install npm@latest -g
```

Install or Update your Homebrew version

```
brew update
```

Install or Update your Yarn version

```
brew install yarn or brew upgrade yarn
```

Install vue command line tool

```
yarn global add @vue/cli
```

## Create a new project

To create your project using the GUI

```
vue ui
```

You can also create it manually

```
vue create proejct_name
```

## Start developing and serve your website

```
vue ui
```

Click into your project and click on "tasks, serve, run task, open app" or you can run:


```
yarn serve
```

There you have it and that's how we get a vue.js project started.
<br>
<hr>
<br>
### References

<a href="https://vuejs.org/" target="blank">Vue.js</a><br>
<a href="https://cli.vuejs.org/" target="blank">Vue Cli 3 documentation</a><br>
<a href="https://bootstrap-vue.js.org/" target="blank">Integrated Bootstrap framework</a><br>
