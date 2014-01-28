# A Ejabberd simple buildout #

travis 

## Introduction ##
This is an excerpt of [collective.xmpp.buildout](https://github.com/collective/collective.xmpp.buildou) which privides a full stack of Ejabberd, Plone and Ngnix.
The purpose of this very basic buildout instead is to run only the Ejabberd server, and make it available 
as [deployments.buildout.production](https://github.com/RedTurtle/deployments.buildout.production) component.


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

Installation on Debian/Ubuntu/etc.
==================================

This buildout compiles Ejabberd from source and to do this, you'll need
the development files of their dependencies.

This is what I needed to install on a fresh(ish) Ubuntu 12.04:

    sudo apt-get install zlib1g-dev erlang libzip2 libzip-dev libbz2-dev libxml2-dev libxslt-dev libpcre3-dev libexpat1-dev libssl-dev


## FAQ ##
### Q: How to set admin password ####
__A:__ In your buildout folder, after running the buildout, you need to do the following:

    ./bin/ejabberdctl register admin localhost your_password

Test that you can access your ejabberd by logging to the admin interface (typically ``http://localhost:5280/admin``).
