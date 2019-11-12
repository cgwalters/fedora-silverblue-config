Fedora Silverblue Config
===

This is a fork of https://pagure.io/workstation-ostree-config/
that is based on [Fedora CoreOS](https://coreos.fedoraproject.org/)
technologies, namely [Ignition](https://github.com/coreos/ignition)
and [rpm-ostree](https://github.com/coreos/rpm-ostree/).

Why?
===

The goal here is to make Fedora CoreOS really more of the "core",
and other editions (such as Silverblue and IoT) derive from it.
From an end user perspective, this makes everything significantly
more coherent.

This config "inherits" directly from [fedora-coreos-config](https://github.com/coreos/fedora-coreos-config)
via a git submodule. The projects also then share build tooling as well, most notably
[coreos-assembler](https://github.com/coreos/coreos-assembler/) and
ideally more of the [FCOS pipeline](https://github.com/coreos/fedora-coreos-pipeline).

Where do I get it?
===

See: http://coreosci-walters-silverblue.s3.amazonaws.com/index.html

Builds are currently running in the "coreosci" cluster, see
https://jenkins-walters-silverblue.apps.coreosci.gcp.devcluster.openshift.com/job/walters-silverblue/job/walters-silverblue-walters-fedora-coreos-pipeline

