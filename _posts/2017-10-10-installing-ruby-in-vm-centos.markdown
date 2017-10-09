---
layout: post
title:  "Installing Ruby in CentOS"
date:   2017-10-10 09:00:00 +1000
categories: ruby
url: installing-ruby-in-centos
---

> The purpose of this documentation is to help with managing the version Ruby in a CentOS VM.

## Lets begin

<a href="https://serverfault.com/questions/508235/uninstall-ruby-on-rails-on-centos-6" target="_blank">Uninstall ruby from CentOS</a>

```
yum remove ruby
```

Provides a list of installed ruby binaries.

```
rpm -qa | grep -i ruby
```

Provides current version of ruby that is running.

```
ruby -v
```

## How to install ruby in Centos version 5

<a href="http://www.heatware.net/linux-unix/how-to-install-ruby-1-8-7-centos-5-5/" target="_blank">I read this to figure out how to install ruby in Centos because intalling RVM in the CentOS VM wasn't working beacuse of a certificate error.</a>

Get the version of ruby as a zip in the root

```
wget ftp://ftp.ruby-lang.org/pub/ruby/2.4/ruby-2.4.2.tar.gz
```

Unzip it

```
tar xvf ruby-2.4.2.tar.gz
```

Enter the folder

```
cd ruby-2.4.2
```

```
./configure --enable-pthread
```

```
make
```

```
make install
```

## Installing ruby locally or on a different VM

Use <a href="https://rvm.io/rvm/install" target="_blank">RVM</a>
