---
layout: post
title:  "How to git tag a branch"
date:   2018-04-01 09:00:00 +1000
categories: git
url: how-to-git-tag-a-branch
---

<blockquote class="blockquote">
Need to tag your branch before you push to origin?
</blockquote>

## Lets begin

Within the branch you want to push to origin, before you push, follow these steps.

```
git fetch --tags
```
```
git describe --tags
```

Now you have to push the tags.

```
git push -f origin master
```

Finally push everything up.

```
git push origin master
```
