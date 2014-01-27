# A varnish 3 buildout #

[TOC]

## Introduction ##
This is the a very basic buildout template to run ejabberd.

## I am feeling lucky! ##
Lucky people read the documentation,
anyway if you have a local copy of this buildout,
try to run this command:
```bash
make
```
## For the impatients ##
To start the buildout:
```bash
python2.7 bootstrap.py &&  ./bin/buildout
```
To launch varnish:
```bash
./bin/ejabberd
```
Installation on Debian/Ubuntu/etc.
==================================

This buildout compiles Nginx and Ejabberd from source and to do this, you'll need
the development files of their dependencies.

This is what I needed to install on a fresh(ish) Ubuntu 12.04:

    sudo apt-get install zlib1g-dev erlang libzip2 libzip-dev libbz2-dev libxml2-dev libxslt-dev libpcre3-dev libexpat1-dev libssl-dev 

```

## FAQ ##
### Q: How can I change the backend port? ####
__A:__ In the file `buildout.cfg`, section `varnish`,
modify the `backend-port` option,
which defaults to:
```config
[varnish]
...
bind = 127.0.0.1:8099
```

### Q: How can I change varnish port? ####
__A:__ In the file `buildout.cfg`, section `varnish`,
modify the `bind` option,
which defaults to:
```config
[varnish]
...
bind = 127.0.0.1:8099
```

### Q: How can I change varnish telnet interface port? ####
```config
[varnish]
...
telnet = 127.0.0.1:8098
```

### Q: How can I change the cache size? ####
__A:__ In the file `buildout.cfg`, section `varnish`,
modify the `cache-size` option,
which defaults to:
```config
[varnish]
...
cache-size = 512M
```
