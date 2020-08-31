Fedora Silverblue Config based on Fedora CoreOS
===

This is a fork of https://pagure.io/workstation-ostree-config/
that is based on [Fedora CoreOS](https://coreos.fedoraproject.org/)
technologies, namely [Ignition](https://github.com/coreos/ignition)
and [rpm-ostree](https://github.com/coreos/rpm-ostree/).

Call this "FCOSB" for short.  And we'll use the abbreviation
"FSB" for the *current* (≤ Fedora 33 Silverblue). 

Why?
===

The goal here is to make Fedora CoreOS really more of the "core",
and other editions (such as Silverblue and IoT) derive from it.
From an end user perspective, this makes everything significantly
more coherent.

## Ignition

All of FSB, IoT and CoreOS use rpm-ostree.  So the biggest
change is that everything would use Ignition instead of
Anaconda (as it exists today).  Perhaps in the future,
Anaconda could gain a mode where it generates an Ignition
config.

While rpm-ostree can be good for "pet" single user machines
including desktops, we also want to encourage even desktop
users to maintain their systems as much as possible
in a "reprovisionable" fashion.  While one can do this with
Anaconda kickstarts today, Ignition also works in cloud
environments and hence a lot of documentation that works for FCOS
will also work for FCOSB.

## Consistent build tooling

The coreos-assembler project makes it *much* easier to build
and test Fedora CoreOS-like systems than "raw" rpm-ostree
plus the existing array of Fedora image build tools.  Everything
needed to build and test comes as one big container image
that can run as an unprivileged container.

How to build
===

This config "inherits" directly from [fedora-coreos-config](https://github.com/coreos/fedora-coreos-config)
via a git submodule. The projects also then share build tooling as well, most notably
[coreos-assembler](https://github.com/coreos/coreos-assembler/) and
ideally more of the [FCOS pipeline](https://github.com/coreos/fedora-coreos-pipeline).

Example to build a Live ISO from this repo:

```
cosa fetch
cosa build
cosa buildextend-metal && cosa buildextend-metal4k
cosa buildextend-live
```

