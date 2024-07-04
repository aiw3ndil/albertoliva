---
layout: post
title:  "install libssl-dev 1.1.1l-1 on ubuntu 1.4"
date:   2024-07-03 20:55:06 +0300
categories: linux
---
```
$ sudo apt install build-essential
$ cd ~/Downloads
$ wget https://www.openssl.org/source/openssl-1.1.1g.tar.gz
$ tar zxvf openssl-1.1.1g.tar.gz
$ cd openssl-1.1.1g
$ ./config --prefix=$HOME/.openssl/openssl-1.1.1g --openssldir=$HOME/.openssl/openssl-1.1.1g
$ make
$ make test # you might get a few tests failing but just ignore
$ make install
$ rm -rf ~/.openssl/openssl-1.1.1g/certs
$ ln -s /etc/ssl/certs ~/.openssl/openssl-1.1.1g/certs
$ cd ~
# let us install older rubies now by using RVM. Hurray!
$ rvm install ruby-3.0.4 --with-openssl-dir=$HOME/.openssl/openssl-1.1.1g # replace ruby-x.x.x to install other older versions
```
