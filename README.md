Metal³ Development Environment
==============================

This repository includes scripts to set up a Metal³ development environment.

Prerequisites:
 * System with CentOS 7
 * Bare metal preferred, as we will be creating VMs to emulate bare metal hosts
 * run as a user with passwordless sudo access

# Current Status

This is still a work in progress.

A management cluster will be launched with the `baremetal-operator`.  A set of
`BareMetalHost` objects will be created for the set of VMs we’ve created to
emulate bare metal servers.  Management of the hosts doesn’t work yet, as the
`minikube` VM is lacking a network interface on the `provisioning` network.

# Instructions

tl;dr - Run `make`.

The `Makefile` runs a series of scripts, described here:

* `01_install_requirements.sh` - Installs all needed packages.

* `02_configure_host.sh` - Create a set of VMs that will be managed as if they
  were bare metal hosts.

* `03_launch_mgmt_cluster.sh` - Launch a management cluster using `minikube` and
  run the `baremetal-operator` on that cluster.

To tear down the environment, run `make clean`.
