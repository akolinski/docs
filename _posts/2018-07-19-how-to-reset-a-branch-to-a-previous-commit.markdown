---
layout: post
title:  "How to reset a branch to a previous commit"
date:   2018-07-19 09:00:00 +1000
categories: git
url: how-to-reset-a-branch-to-a-previous-commit
---

<blockquote class="blockquote">
    Sometimes you might have committed and pushed something that you need to revert. No worries!
</blockquote>

## Lets begin

First you need to find the commit [id] from your Github/Bitbucket repo. Then use this command.

```
git reset --hard 8cec4c7b726
```

Once reset you can add a commit message to show what you've done.

```
git commit -m "reverting branch back to 8cec4c7b726"
```

Then you need to force push the change on the branch.

```
git push -f origin [branch_name]
```
