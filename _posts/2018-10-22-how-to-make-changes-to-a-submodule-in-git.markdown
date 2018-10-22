---
layout: post
title:  "How to make changes to a submodule in git"
date:   2018-10-22 09:00:00 +1000
categories: git
url: how-to-make-changes-to-a-submodule-in-git
---

<blockquote class="blockquote">
    When working in a repository you may be version controlling a separate folder using a submodule. This is how to make a change and then push that change in the repo.
</blockquote>

## Lets begin

Let's say our repositories base path is:

```
cd /my_project
```

This folder is where we have a .git folder to version control the entire /myproject source code.

Now let's move into the folder where we version control something separately, for example an add_on called "boom".

```
cd /my_project/add_ons/boom
```

"boom" is separately version controlled and has it's own .git folder. We should see a hash next to the branch name in terminal. It'll show what hash we are currently checked into. This hash should match the hash seen in the repository for "/my_project". If it isn't, we need to make sure we are checked into the correct hash and apply our changes.

For example an issue could be that the "/my_project" repository is showing the wrong hash for the folder "/my_project/add_ons/boom" with a hash of "686312069e6" but we need it to be "c2ef32b38b1".

First of all we need to go into the folder of our add_on.

```
cd /my_project/add_ons/boom
```

Then checkout to the correct branch.

```
git checkout c2ef32b38b1
```

Then move back to our /my_project folder which will show a modified change in our git status.

```
cd /my_project
```

Please add and commit these modified changes.

```
git add .
```

```
git commit -m "Changed hash to correct hash"
```

```
git push origin <branch_name>
```

There we have it, the hash for the add_on will now be correct. Go to the repository and view the folder and the hash should show as correct.
