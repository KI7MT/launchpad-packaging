# WSJT-X Developer Tools Installation

| Application Data ||
| ---| --- |
| Package       | [wsjtx-metadev]
| Version       | 0.0.1-1
| Distributions | Ubuntu Bionic, Xenial, and others
| Arch          | i386, amd64, arm64, armel, armhf, ppc64el
| Description   | Development Tools for Compiling [WSJT-X][] and [Hamlib][]

>NOTE: This meta-package will install a substantial number application library's,
>frameworks, and support files. Installation time may vary based on internet and
>system speeds; plan accordingly.

## Table of Contents

- [Overview](#overview)
- [Install on Ubuntu Native](#install-on-ubuntu-native)
- [Install on Debian Buster](#install-on-debian-buster)
- [Install on Linux Mint](#install-on-linux-mint)
- [Additional Distributions](#additional-distributions)
- [Bug Reports](#bug-reports)

## Overview

If you are simply running [WSJT-X][], you `do not` need this package. If you
are a developer, or want to compile [WSJT-X][] | [Hamlib][], this package will
assist in adding the required build dependencies.

## Install on Ubuntu Native

````shell
# Step-1: Add the PPA
sudo add-apt-repository -y ppa:ki7mt/wsjtx-metadev

# Step-2: Update repository list(s)
sudo apt update

# Step-3: Install
sudo apt install wsjtx-metadev
````

## Install on Debian Buster

````shell
# All actions are performed in a terminal

# Step-1: Add the repository key
sudo apt-key adv --recv-keys --keyserver keyserver.ubuntu.com 862549F9
sudo apt update

# Step-2: Edit source list, add the PPA repository
sudo nano /etc/apt/sources.list

# Add the following
# -----
deb http://ppa.launchpad.net/ki7mt/wsjtx/ubuntu bionic main
# -----

Save and exit

# Step-3: Update repository list(s)
sudo apt update

# Step-4: Install
sudo apt install wsjtx-metadev
````

## Install on Linux Mint

````shell
# Step-1: Add the PPA
sudo add-apt-repository -y ppa:ki7mt/wsjtx-metadev

# Step-2: Update repository lists
sudo apt update

# Step-3: Install
sudo apt install wsjtx-metadev
````

## Additional Distributions

As and when distribution information is made available, it will be
added to this section. If you have specific platform specific notes to share, fill out an [Issue][] report on Github.

## Bugs Reports

For bugs identified, create and [Issue][] report on Github.

[Matrix]: https://github.com/KI7MT/launchpad-packaging#release-relationship-matrix
[WSJT-X]: https://physics.princeton.edu/pulsar/k1jt/wsjtx.html
[Hamlib]: https://hamlib.github.io/
[Issue]: https://github.com/KI7MT/launchpad-packaging/issues
[wsjtx-metadev]: https://launchpad.net/~ki7mt/+archive/ubuntu/wsjtx-metadev