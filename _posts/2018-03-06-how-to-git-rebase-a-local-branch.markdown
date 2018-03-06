---
layout: post
title:  "How to git rebase a local branch"
date:   2018-03-06 09:00:00 +1000
categories: git
url: how-to-git-rebase-a-local-branch
---

<blockquote class="blockquote">
Need to rebase your local branch before creating a pull request?
</blockquote>

## Lets begin

Within your current local branch add all of your current changes, commit and push them to origin.

```
git add .
```
```
git commit -m "My wonderful message to help understanding the feature developed"
```
```
git push origin mylocalbranch
```

Checkout out to master and and pull origin

```
git checkout master
```
```
git pull origin master
```

Checkout back to your local branch and rebase from master. Then force push the changes to origin.

```
git checkout mylocalbranch
```
```
git rebase master
```
```
git push -f origin mylocalbranch
```

<div class="alert alert-warning">
<h4 class="alert-heading mt-2 mb-3"><i class="fas fa-exclamation-circle mr-2"></i> Be careful!</h4>
<p class="mb-0">If someone else is working on the same branch as you 'force pushing' will lose their work. There is a safer way. Merging master into your branch will allow you to push without a force. However you will now have the problem of a messy git commit history. You can rebase interactively and squash your commits into a single commit to make it nice and tidy.</p>
<hr>
<p class="mb-0">
Here is the stack overflow link to the question I read through <a class="alert-link" href="https://stackoverflow.com/questions/7929369/how-to-rebase-local-branch-with-remote-master" target="_blank">How to rebase local branch with remote master</a>. I also read <a class="alert-link" href="https://makandracards.com/makandra/527-squash-several-git-commits-into-a-single-commit" target="_blank">squash several Git commits into a single commit</a> to learn how to clean up my local branches commit history before creating a pull request.</p>
</div>