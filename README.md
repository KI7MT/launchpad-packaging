# Launchpad Packaging

Debian, Ubuntu, and Descendent Distribution Package Installation via Launchpad

## Introduction

>"Successful open source projects are usually initiated by someone with a clear
>vision and also the knowledge to set about turning that vision into reality".
>
>-- *[Mark Shuttleworth, CEO of Canonical Ltd.][]*

----

## Table of Contents

1. [Overview](#overview)
1. [Parent-Child Compatibility](#parent-child-compatibility)
1. [Release Relationship Matrix](#release-relationship-matrix)
1. [Example Installations](#example-ppa-installations)
    - [PPA Install on Debian Buster](#ppa-install-on-debian-buster)
    - [PPA Install on Linux Mint](#ppa-install-on-linux-mint)
1. [Conclusion](#conclusion)

## Overview

Unlike [Debian][], [Ubuntu][] employs a platform called [Launchpad][] to build,
and ultimately deliver, software packages for end-user consumption. While not
absolute, most [third party variants][], including all [Ubuntu Flavors][],
can--most do--use [Launchpad][] for package installation and automated updates.
The vast majority of [Ubuntu][] packages follow the [Debian Maintainers Guide][]
(there are some exceptions), which is considered the base for [Debian][] package
creation and distribution.

Using [Launchpad][], maintainers create a [Personal Package Archives][] (`PPA`)
to deliver software not yet available in the main repository, variants of
distributed software, development software, or any combination thereof. Users
then install the `PPA`, which itself is a repository, for consuming the
application.

## Parent-Child Compatibility

[Ubuntu][] is a direct descendent (child) of [Debian][] (parent). As such; package
versions, naming, and compatibility are tightly coupled. This coupling transcends
distributions which use [Ubuntu][] as the parent. With [Ubuntu][] in the
middle via [Launchpad][], many popular distributions such as [Linux Mint][],
[elementry os][], and [Linux Lite][] (just to name a few) can leverage
[Launchpad][] for application installation and updates.

In the case of [Debian][], the parent-child coupling means that
many--certainly not all--[Ubuntu][] packages distributed via [Launchpad][] can
also be installed with the same semantics.

In short, if your distribution is a direct descent of [Ubuntu][] or you
are using [Debian][] proper, odds are good that you too can use [Launchpad][]
to install the application in question.

The following matrix describes a few popular parent-child relationships, and which
[Ubuntu][] repository (via [Launchpad][]) you should use for that relationship.

### Release Relationship Matrix

In the following matrix, [Debian][] is the parent which has a child named
[Ubuntu][] who in turn has it's own child named [Linux Mint][]. [Ubuntu][] acts
in the capacity of both child and parent forming a bridge between the
distributions. This relationship enables a great deal of flexibility in terms
of cross-distribution package compatibility.

|   Debian       |    Ubuntu       | Mint        | Ubuntu Status |Repository
|:--------------:|:---------------:|:-----------:|:-------------:|:------------|
| sid dev        | Cosmic (18.04)  | mint dev    | eol Jun 2019  | Cosmic      |
| Buster (10)    | Bionic (18.04)  | 19 series   | eol Apr 2023  | Bionic      |
| Stretch (9)    | Xenial (16.04)  | 18 series   | eol Apr 2021  | Xenial      |
| Jessie (8)     | Trusty (14.04)  | 17 series   | eol Apr 2019  | Trusty      |

All Parent-Child relationships have three things in common:

1. The majority of source-code-packaging originates from [Debian][] (parent).
1. [Launchpad][] can install applications on both [Linux Mint][] (child) and
   [Debian][] (parent) when using the correct repository.
1. All three use the same build-process to deliver `*.deb` packages.

This sharing of source-code coupled with a standards-based packaging approach
allows a great deal of flexibility for the Parent and Child, even if the
distribution acts in multiple capacities (Parent and Child).

### Example PPA Installations

From the [Matrix](#release-relationship-matrix) above, use the corresponding
[Launchpad][] repository:

- Debian Buster or Mint 19 series ==> `Bionic`
- Debian Stretch or Mint 18 series ==> `Xenial`

### PPA Install on Debian Buster

This example is for `Debian Buster (10)` and [WSJT-X][] , a popular Amateur
Radio Application.

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

# Step-3: Update repository list(s), and install WSJT-X
sudo apt update
sudo apt install wsjtx
````

With the application is installed via the `PPA` method, any updates to [WSJT-X][]
will be automatically delivered during normal package `update` and `upgrade`
cycles.


### PPA Install on Linux Mint

The same example from above, but for [Linux Mint][]

>NOTE: As [Linux Mint][] is a child of [Ubuntu][], which happens to use
>[Ubuntu][] repositories for updates, we `do not` need to edit
>sources.list as the [Ubuntu][] `main` repository is already present;
>thus, we simply add the `PPA`, and install the application.

````shell
# Step-1: Add the PPA
sudo add-apt-repository -y ppa:ki7mt/wsjtx

# Step-2: Update repository lists
sudo apt-get update

# Install WSJT-X
sudo apt-get install wsjtx
````

## Conclusion

[Launchpad][] is a powerful tool, not only for developers, but for those that
take the time to understand it's relationships between Parent and Child
distributions. With a little effort, users can dramatically expand package
availability, and ease the burden of build software from source in order to
satisfy a specific need.

[Mark Shuttleworth, CEO of Canonical Ltd.]: https://www.markshuttleworth.com/archives/date/2003/1
[Debian]: https://www.debian.org/ "debian, the universal operating system"
[Ubuntu]: https://www.debian.org/ "debian, the universal operating system"
[Launchpad]: https://launchpad.net/ "Ubuntu package management system"
[Ubuntu Flavors]: https://www.ubuntu.com/download/flavours "Variants of Ubuntu"
[third party variants]: https://en.wikipedia.org/wiki/List_of_Linux_distributions#Third-party_distributions
[Debian Maintainers Guide]: https://www.debian.org/doc/manuals/maint-guide/index.en.html
[Personal Package Archives]: https://help.ubuntu.com/community/PPA "what is a PPA"
[Linux Mint]: https://linuxmint.com
[elementry os]: http://elementary.io/
[Linux Lite]: https://www.linuxliteos.com/
[WSJT-X]: https://physics.princeton.edu/pulsar/k1jt/wsjtx.html