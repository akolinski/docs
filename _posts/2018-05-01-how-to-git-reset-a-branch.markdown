---
layout: post
title:  "How to git reset a branch"
date:   2018-05-01 11:00:00 +1000
categories: git
url: how-to-git-rest-a-branch
---

<blockquote class="blockquote">
Need to reset your branch? Lets go back in time.
</blockquote>

## Lets begin

Within the branch you want to revert back to a previous commit. In Github or whatever version control app you are using find out the hash of the commit you want to revert to. Once retrieved follow these commands.

```
git reset --hard ea9473eacd2
```

Now you have to push the tags.

```
git commit -m "reverting branch back to ea9473eacd2"
```

Finally push everything up.

```
git push -f origin master
```
