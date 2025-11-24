# Grassroots Installer

## Introduction

This repo contains tools to automatically deploy all of the components and third-party tools for a Grassroots Infrastructure. Currently this is for Linux with both MacOS and Windows versions to follow.


## Linux

For Linux, the included script `install_grassroots_linux.sh` can be used. 
To configure your installation, you need to set a number of variables and this is done in a file called `user.prefs`. 
An example file is included in this repo, so if you haven't already, use this to create an initial version of your 'user.prefs' which you can do by

```
cp example_user.prefs user.prefs
```

You can then proceed to edit `user.prefs` for your set-up. 
This file contains a number of configuration optionss which are detailed below.


 * **INSTALL_DIR**: This is the directory in which the compiled Grassroots tools will be installed. 
 
     _e.g._ INSTALL_DIR=/opt/grassroots
	
 * **SRC_DIR**: This is the directory where the various Grassroots source repositories will be checked out to. 
 This is currently set to `"$( cd "$(dirname "$0")" ; pwd -P )"` which is the current directory.

 * **ARRAY_DEC**: This is the identifier for array declarations. For Bash this is `declare -A` and in zsh is `typeset -A` 
 
 * **LOCAL_VAR_ARG** =-n

 * **LIB_SUFFIX**: This is the library extension for this platform _e.g._ `so` for linux, `dylib` for mac
 
     _e.g._ `LIB_SUFFIX=so`

 * **SUDO**: If you need sudo rights to install grassroots then set this to `sudo`, otherwise leave it blank
 
     _e.g._ `SUDO=sudo`

 * **PLATFORM**: Set this to either `linux` or `mac` depending upon your OS

 * **GRASSROOTS_PROJECT_DIR**: The path where you want the Grassroots source code to be checked out to. 
 By default this is set to `$SRC_DIR/Projects/grassroots`.

 * **GRASSROOTS_INSTALL_DIR**: This is the root path that grassroots will be installed to. 
 By default this is set to `$INSTALL_DIR/grassroots`

 * **USER**: If you are needing to use sudo, due to permissions, to install to your chosen destination, then this allows
 you to change the ownership, after the installation, to another user and not _root_. 
 
   _e.g._ to set the owner to `billy`, use `USER=billy`

 * **GROUP**: If you are needing to use sudo, due to permissions, to install to your chosen destination, then this allows
 you to change the ownership, after the installation, to another group and not _root_. 
 
   _e.g._ to set the group to `dev`, use `GROUP=dev`

 * **APACHE_PORT**: This is the TCP port that Apache will be listening on. 

   _e.g._ to listen on port 2000 then you will need `APACHE_PORT=2000`

 * **APACHE_GRASSROOTS_LOCATION**: This is the web path that Grassroots backend server will be working on and will be the 
 value used in the _conf/extra/grassroots.conf_ file within Apache to specify the web address Apache will use for communicating
 with the Grassroots server.
 By default this is set to `grassroots/public_backend`

 * **GRASSROOTS_SERVER_CONFIG**: This is the name of the Grassroots config that we will generate within the _config_ folder in Grassroots.

 * **PROVIDER_NAME**: In the metadata where the Grassroots server describes itself, this is the name that it will use.

 * **PROVIDER_DESCRIPTION**: In the metadata where the Grassroots server describes itself, this is the description that it will use.

 * **PROVIDER_LOGO**: In the metadata where the Grassroots server describes itself, this is the web path for the logo that it will use.

   _e.g._ setting `PROVIDER_LOGO="grassroots/logo.png"` would request _grassroots/logo.png_ from the Apache server.

 * **MONGORESTORE**: If you are installing the demo databases in MongoDB, set this to the path of the mongorestore tool that comes with MongoDB. 

 * **FIELD_TRIALS_DB**: This is the name you want to give to the field trials database within MongoDB

   _e.g._ to set it to _field\_trials_, use `FIELD_TRIALS_DB=field_trials`

 * **DJANGO_URL**: This is the web address that the Django server will be running on and by default this will be `http://localhost:8000`


 * **PDFLATEX**: This is the path to pdflatex which is used to generate the Study handbooks. Go to [TexLive](https://www.tug.org/texlive/) 
	for more information on how to install LaTeX.

 * **GEOIFY_API_KEY**: As part of the Field Trials service it uses [Geoify](https://www.geoapify.com/) to get maps for given locations. 
 This service is free but requires getting an API key to be used and, once you have it, use this key to specify it.


 * **HTTP**: Set this to `http` or `https` depending upon if your server is set up for secure traffic or not.

