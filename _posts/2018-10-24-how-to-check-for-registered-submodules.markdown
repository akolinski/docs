---
layout: post
title:  "How to check for registered submodules"
date:   2018-10-24 09:00:00 +1000
categories: git
url: how-to-check-for-registered-submodules
---

<blockquote class="blockquote">
    When working in a repository you may need to check what submodules are registered.
</blockquote>

## Lets begin

Most of the time you can do this by opening the .gitmodules file in the root folder. Which will list the submodules registered to the project. So when you run the command below it will bring in the submodules.

```
git submodule update --init
```

Sometimes you may run into an issue in a repository when other unidentified modules are outlined when running the command above.

Check which submodules are registered in the cache using this command:

```
git ls-files --stage | grep 160000
```

You will now have a list of the submodule in the stage area. Remove any paths that you do not want.

```
git rm --cached Example/Folder
```

Try the update submodule command again and everything will be dandy!
<br>
<hr>
<br>
### Reference

<a href="https://stackoverflow.com/questions/4185365/no-submodule-mapping-found-in-gitmodule-for-a-path-thats-not-a-submodule" target="blank">No submodule mapping found in .gitmodule for a path that's not a submodule</a>
