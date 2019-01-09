# Launchpad Packaging

Repository for Debian or Ubuntu Packages Distributed via Launchpad

>Successful open source projects are usually initiated by someone with a clear
> vision and also the knowledge to set about turning that vision into reality.
>
>-- *[Mark Shuttleworth, CEO of Canonical Ltd.][]*


## Table of Contents

- [Overview](#overview)
- [Compatibility Matrix](#compatability-matrix)

## Overview

Unlike [Debian][], [Ubuntu][] employs a platform called [Launchpad][] to build,
and ultimately deliver, software packages for end-user consumption. While not
absolute, most [third party variants][], including all [Ubuntu Flavors][],
can--most do--use [Launchpad][] for package installation and automated updates.
The vast majority of [Ubuntu][] packages follow the [Debian Maintainers Guide][]
(there are some exceptions), which is considered the base for [Debian][] package
distribution.

Using [Launchpad][], maintainers create a [Personal Package Archives][] (`PPA`)
to deliver software not yet included in the main distribution, variants of
distributed software, development software, or any combination thereof. Users
then install the `PPA`, which itself is a repository, for consuming the
application.

## Compatibility Matrix

TODO: (work in progress)

[Mark Shuttleworth, CEO of Canonical Ltd.]: https://www.markshuttleworth.com/archives/date/2003/1
[Debian]: https://www.debian.org/ "debian, the universal operating system"
[Ubuntu]: https://www.debian.org/ "debian, the universal operating system"
[Launchpad]: https://launchpad.net/ "Ubuntu package management system"
[Ubuntu Flavors]: https://www.ubuntu.com/download/flavours "Variants of Ubuntu"
[third party variants]: https://en.wikipedia.org/wiki/List_of_Linux_distributions#Third-party_distributions
[Debian Maintainers Guide]: https://www.debian.org/doc/manuals/maint-guide/index.en.html
[Personal Package Archives]: https://help.ubuntu.com/community/PPA "what is a PPA"
1