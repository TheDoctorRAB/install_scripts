PyNE Install Scripts
====================

In this repository, you will find both bash scripts and dockerfiles for various
Debian-derived systems. These scripts will install PyNE and its dependencies to
either your device or an [image](https://docs.docker.com/get-started/#images-and-containers).
Docker allows users to build these images and to operate them separate from the rest of
your device.

You can download Docker [here](https://docs.docker.com/get-docker/).

Bash Scripts (*.sh)
-------------------

These scripts will install PyNE and its dependencies on the system.
An install script is available for different versions of Ubuntu operating systems. 
The intention of these scripts is that PyNE can be ready to use on a clean install of any of
the supported operating systems: if users have customized/configured their python environment 
beyond the default OS installation, we can't guarantee that the scripts will work.

Furthermore, the user should choose either to build a stable release version of PyNE or the current
develop branch of PyNE by supplying a second argument. 

Example for installing the most recent stable branch on Ubuntu 20.04:

    ./ubuntu.sh stable
    
Example for installing the develop branch on Ubuntu:
	
	./ubuntu.sh dev

**!!!WARNING!!!:** 

Those scripts are intended to be used on python3 environment then assumes that 
your system uses python3 as default when the `python` executable is run.
To test which default Python version your system is using, run in a terminal:
`python --version`.
If it returns `Python 3.x.y`, you should be able to use our install scripts.
If it returns `Python 2.x.y`, our install 
script will not work as is on your system. You will need to update the default python 
version. To do so you can follow those 
[instruction](https://gist.github.com/patrickmmartin/5b6b2ddecd29d6a1b2ffee2d8eea31ec).

Docker Builds (*.dockerfile)
----------------------------

These Dockerfiles can be used to build a docker image that has PyNE
installed. The dockerfile chosen will build on the version of Ubuntu
listed (18.04 or 20.04). Furthermore, the user may choose either
to build a stable version of PyNE ("-stable") or the current develop
branch of PyNE ("-dev") for each. Example for building a docker image
of the latest stable branch of PyNE based on Ubuntu 20.04:

    docker build -f ubuntu_20.04-stable.dockerfile -t pyne-ubuntu-20.04-stable .
