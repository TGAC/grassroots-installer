# Grassroots Installer

## Introduction

This repo contains tools to automatically deploy a Grassroots Infrastructure. 

## Platforms

### Linux

For Linux, the included script `install_grassroots_linux.sh` can be used. 
There are a number of configuration options at the start of the script which are detailed below.

0
 * *INSTALL_DIR*: This is the directory in which the compiled Grassroots tools will be installed. 
 * *SRC_DIR*: This is the directory where the various Grassroots source repositories will be checked out to. 
This is currently set to `"$( cd "$(dirname "$0")" ; pwd -P )"` which is the currrent directory.



TO DO:

# array declarations are declare -A for bash and typeset -A for zsh
ARRAY_DECL="declare -A"
#ARRAY_DECL="typeset -A" 

# For Bash set this to -n, for zsh, leave blank
LOCAL_VAR_ARG=-n

# This is the library extension for this platform e.g. so for linux, dylib for mac
LIB_SUFFIX=so

# If you need sudo rights to install grassroots
# then set
# 
# SUDO=sudo
#
SUDO=

# Set this to either linux or mac depending upon your OS
PLATFORM=linux

# The path where you want the Grassroots source code to be checked out to
GRASSROOTS_PROJECT_DIR=$SRC_DIR/Projects/grassroots


# The root path that grassroots will be installed to
GRASSROOTS_INSTALL_DIR=$INSTALL_DIR/grassroots


# If you are needing to use sudo to install
# then this will set the owner
USER=billy


# The port to run apache on
APACHE_PORT=2000

# This is the web path that Grassroots backend server will be working on
APACHE_GRASSROOTS_LOCATION=grassroots/public_backend

# This is the name of the Grassroots config that we will generate
GRASSROOTS_SERVER_CONFIG=public

# This is the name that this Grassroots Server will use
PROVIDER_NAME=localhost

# This is the description that this Grassroots Server will use
PROVIDER_DESCRIPTION="Grassroots running on localhost"

# This is the logo that this Grassroots Server will use
PROVIDER_LOGO="grassroots/logo.png"

# Set this to the path of the mongorestore tool
MONGORESTORE=mongorestore

# The name to give to the field trials database
FIELD_TRIALS_DB=field_trials


# This is the web address that the Django server will be running on
DJANGO_URL="http://localhost:8000"


# The path to pdflatex used to generate the Study handbooks
PDFLATEX="/opt/texlive/bin/x86_64-linux/pdflatex"


# your geoify api key, see https://www.geoapify.com/ for details
GEOIFY_API_KEY=""


# Set this to http or https depending upon if your server is
# set up for secure traffic or not
HTTP="http"

