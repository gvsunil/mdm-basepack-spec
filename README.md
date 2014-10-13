mdm-basepack-spec
=================

A basepack specification defines the environment required to setup an app. The basepack scripts use this specification to create the base AMI, which can be used to install the app.

## packages.ini

In a typical INI format, specify the [apt_sources], [apt_key_urls], [apt_repositories] and [apt_packages] in different sections. 

## virtualenvs/

1. Under this directory, create one file each for all virtual environments required by the app. In this case, the only virtualenv needed is cloudmdm.
2. The format of the file is INI. Inside the file, specify all the python packages under the section [virtualenv_packages]

## custom/

1. pre_install_apt_packages.sh: This script is run before any apt packages are installed. Any custom pre-install setup must go here.
2. post_install_packages.sh: This script is run after all packages (including virtualenvs) are installed. Any post-install setup must go here.
