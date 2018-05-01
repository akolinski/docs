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

That will return to you the previous tag. Which you can now iterate and go up one version number. Of course it'll only return a tag if it previously had one.

```
git tag -a tag-1.0.0 -m 'tag-1.0.0'
```

Now you have to push the tags.

```
git push --tags
```

Finally push everything up.

```
git push origin branch_name
```
