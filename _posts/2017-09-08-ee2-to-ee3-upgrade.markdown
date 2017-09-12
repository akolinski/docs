---
layout: post
title:  "EE2 to EE3 upgrade"
date:   2017-09-08 10:28:48 +1000
categories: expressionengine
url: upgrading-from-expressionengine-2-to-expressionengine3
---

Okay lets start upgrading EE2 to EE3.

Currently we have two instances running.

1. EE2 instance
2. A fresh EE3 instance

## EE2 instance

- Put current EE2 instance into a new vagrant box with current database.
- Libraries / core / Environment.php throwing errors

We had to change the path in these files

public/libraries/core/Environment.php
modified:   public/libraries/core/exception/ArgumentException.php
modified:   public/system/expressionengine/config/config.php
modified:   public/system/expressionengine/config/database.php
modified:   public/system/expressionengine/third_party/ep_better_workflow/libraries/ep_status_transition.php

from

```
require_once ('core/Environment.php');
```
to

```
require_once ('libraries/core/Environment.php');
```

## Edit config.php

Update the stash_static_basepath && stash_file_basepath in config.php

from

```
/usr/local/www-shared/ee-acer/assets/templates/stash-cache/';
```

to

```
assets/templates/stash-cache/
```


## So we are going to rewrite this so that it's super simple.

## Vagrant box

Create a new virtual host.

Sites available show the conf.
Sites enabled are sim links that enable the sites available.

```
vagrant@scotchbox:~$ sudo su
root@scotchbox:/home/vagrant# cd /etc/apache2/
root@scotchbox:/etc/apache2# ll
drwxr-xr-x   2 root root  4096 Nov  3  2015 sites-available/
drwxr-xr-x   2 root root  4096 Jul 10  2015 sites-enabled/
```

You need to copy out this files if you want to be able to destroy these newly created scripts or setup a provising script in order to get it to work.

## Upgrading from ExpressionEngine 2 to ExpressionEngine3

When we are ready we need to copy files from EE2 old vm to this current EE2 (public folder). So we have the latest codebase and ensure that the files are not being tampered with. Once in place we have a few of things to do:

### 1. Uninstall these modules and delete folders

I think this step is only needed if we actually bring files from the EE2 instance currently on our old VM's to this new EE2 instance. This is because currently we cannot remove ACER Workflow from the current website.

- ACER Workflow
- NSM Live Look
- Sitemap

### 2. next steps



#### Resources

[Upgrading from ExpressionEngine 2][ee2-upgrade]

[ee2-upgrade]: https://docs.expressionengine.com/latest/installation/upgrade_from_2.x.html
[ee-conversion]:   https://docs.expressionengine.com/latest/development/conversion/index.html
[ee3-addon-setup]: https://docs.expressionengine.com/latest/development/addon_setup_php_file.html
[ee3-co-styles]: https://docs.expressionengine.com/latest/development/cp_styles/index.html
