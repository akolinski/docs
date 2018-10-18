---
layout: post
title:  "How to create a git patch"
date:   2018-10-18 09:00:00 +1000
categories: git
url: how-to-create-a-git-patch
---

<blockquote class="blockquote">
    Creating a patch in GIT can help apply changes with the use of a command.
</blockquote>

## Lets begin

<ol>
    <li>Checkout master/stable branch, create a new branch</li>
    <li>Make the changes and then add and write a nice commit message</li>
    <li>Run the command below. This will create a new file in current working directory.</li>
    <li>Afterwards move the patch file into a well named folder like /excluded for later use.</li>
</ol>

```
git format-patch -1
```

<div class="alert alert-warning">
    <h4 class="alert-heading mt-2 mb-3"><i class="fas fa-exclamation-circle mr-2"></i> Please note!</h4>
    <p class="mb-0">Only commit the patch file to the repo and apply the patch when needed. Following the steps underneath.</p>
</div>

### Applying a patch (No output means patch was applied)

```
git apply patch_file
```

### Revert applied patch

```
git apply -R patch_file
```
