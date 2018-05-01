---
layout: post
title:  "How to git reset a branch"
date:   2018-05-01 11:00:00 +1000
categories: git
url: how-to-git-rest-a-branch
---

<blockquote class="blockquote">
Need to revert to a previous commit? Lets go back in time.
</blockquote>

## Lets begin

Within the branch you want to revert to a previous commit. In Github or whatever version control app you are using find out the hash of the commit you want to revert to. Once retrieved follow these commands.

```
git reset --hard ea9473eacd2
```

Leave a nice commit message informing that you have reverted.

```
git commit -m "Reverting branch to ea9473eacd2"
```

Finally force push everything.

```
git push -f origin master
```
