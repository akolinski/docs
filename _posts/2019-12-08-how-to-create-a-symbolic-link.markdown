---
layout: post
title:  "How to create a symbolic link"
date:   2019-12-08 09:00:00 +1000
categories: server
url: how-to-create-a-symbolic-link
---

<blockquote class="blockquote">
    Symbolic links are basically advanced shortcuts. Create a symbolic link to an individual file or folder, and that link will appear to be the same as the file or folder to Windows—even though it’s just a link pointing at the file or folder.
</blockquote>

## Let's go 

<code>cd /etc/httpd/conf.d</code><br>
<code>sudo !!</code><br>
<code>ln -s /usr/local/www/system/conf/system.conf system.conf</code><br>
<code>systemctl restart httpd</code><br>
