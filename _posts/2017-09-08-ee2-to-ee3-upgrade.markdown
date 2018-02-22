---
layout: post
title:  "EE2 to EE3 upgrade"
date:   2017-09-08 10:28:48 +1000
categories: expressionengine
url: upgrading-from-expressionengine-2-to-expressionengine3
---

<blockquote class="blockquote">
Okay lets start upgrading EE2 to EE3.
</blockquote>

Currently we have two instances running.

1. in the public folder we have our old EE2 instance running
2. in the ee3 folder we have a fresh install of ee3 for testing purposes
3. to run the upgrade and then revert back duplicate the public folder and rename to public_before_upgrade and take a dump of the db.

You are now in a safe place.

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
/usr/local/www-shared/ee-anon/assets/templates/stash-cache/';
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

When we are ready we need to copy files from EE2 old vm to this current EE2 (public folder). So we have the latest codebase and ensure that the files are not being tampered with. Once in place we have a few of things to do.

> Backup the current EE2 database and codebase.

### 1. Uninstall these modules and delete folders

I think this step is only needed if we actually bring files from the EE2 instance currently on our old VM's to this new EE2 instance. This is because currently we cannot remove ANON Workflow from the current website.

- ANON Workflow
- NSM Live Look
- Sitemap
- Supersearch

* Make sure that any other modules, plugins, accessories, extensions and fieldtypes aren't included!

### 2. Follow steps from EE docs

Note * In the documentation where they recommend "putting ExpressionEngine 3 compatible third-party add-ons into the system/user/addons/ directory now." Be sure to move the addons themes folders as well.

[Follow the steps from 1 to point 6][ee2-upgrade]

### 3. Set permissions

chmod 777 system/user/config/config.php
chmod 777 system/user/cache/
chmod 777 system/user/templates/

Boom, we should now have EE3 running.

### 4. After upgrade (Can we do this before the upgrade? Does it even matter?)

1. Delete all calls to ep_better_workflow in exp_extensions table
1. Delete all calls to Nsm_live_look_ext / dummy_hook in exp_extensions table
1. Delete all calls to Absolute_total_results_ext in exp_extensions table
2. Delete all exp_ep.. tables
3. Delete all exp_super_search.. tables
4. Delete exp_sitemap table ? TEST
5. Delete exp_proform tables ?  TEST
5. Delete exp_nsm tables ? TEST
6. Delete exp_freeform tables ? TEST
7. Remove Ep_better_workflow rows from exp_actions table
8. Remove Super_search row from exp_actions table
9. Open exp_modules and delete any references to modules that have been already uninstalled
10. Install all the plugins that need to be installed. Previous version of EE had plugin just appear we now need to actually click install.
11. To be removed 'parent_is_bwf_draft' from `exp_relationships` for publisher to be able to install.

[ee2-upgrade]: https://docs.expressionengine.com/v3/installation/upgrade_from_2.x.html
[ee-conversion]:   https://docs.expressionengine.com/latest/development/conversion/index.html
[ee3-addon-setup]: https://docs.expressionengine.com/latest/development/addon_setup_php_file.html
[ee3-co-styles]: https://docs.expressionengine.com/latest/development/cp_styles/index.html