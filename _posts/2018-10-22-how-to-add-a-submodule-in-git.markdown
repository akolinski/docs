---
layout: post
title:  "How to add a submodule in git"
date:   2018-10-22 08:00:00 +1000
categories: git
url: how-to-add-a-submodule-in-git
---

<blockquote class="blockquote">
    When working in a repository you may want to version control a separate folder, this is how to do it.
</blockquote>

## Adding a submodule in an existing repository

Please ensure the folder doesn't already exist. If it does please remove that folder.

```
git rm -r -f path_to_folder
```

&

```
rm -r -f path_to_folder
```

Then add a submodule using the command below from the root. Where the .gitmodules file lives.

```
git submodule add url_to_repo path_you_want_it_to_clone_too
```

You can then check what the registered submodules are using this command.

```
git ls-files --stage | grep 160000
```

## Adding a new submodule to remote

First of all copy the folder into a folder on your computer out of your existing project. Then cd into the folder.

```
cd /my_submodule
```

Now follow these commands:

```
git init
```

```
git add --all
```

```
git commit -m "Initial Commit"
```

The next line will be the remote ssh address for the repository that you need to setup using Github.

```
git remote add origin ssh://git:1234/adam/name_of_repo.git
```

```
git push -u origin master
```

We have just made that folder associated with our created git repository.

Next let's bring in that submodule into our current working project.

```
cd /my_project
```

Checkout into our working branch.

```
git checkout <branch_name>
```

Make sure we have no changes and the latest code.

```
git status
```

```
git pull origin <branch_name>
```

Let's be careful and branch out to a new branch.

```
git checkout –b add_submodule
```

Next we add the submodule to the project we are currently working within.

```
git submodule add ssh://git:1234/adam/name_of_repo.git add_ons/name_of_repo
```

Now lets go into that submodule and add, commit + push all of our changes.

```
cd add_ons/name_of_repo
```

```
git status
```

```
git commit –m "Adding submodule"
```

```
git push origin <branch_name>
```

That's it we have added a submodule to our project.
