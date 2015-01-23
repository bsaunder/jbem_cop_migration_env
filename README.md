# JBEM CoP Standard Migration Environment
This repo contains the scripts and code necessary to build a standard development environment that can be used for migrating JBoss based applications.

## Environment Information
The default VM that is built and configured is a VirtualBox VM that can be run on any OS. The VM is built on Fedora 20 x64 and contains the following software packages:
 - Update
 - As
 - Provisioned

## Building the Environment
Follow the steps below to build the Environment
 - Install the Required Software
  - [Packer v0.7.5 or Greater](https://packer.io/downloads.html)
  - [VirtualBox v4.3.20 or Greater](https://www.virtualbox.org/wiki/Downloads)
  - [Vagrant v1.7.2 or Greater](https://www.vagrantup.com/downloads.html)
 - Build the Vagrant Base image by following the directions in [packer/README.md]()

## Default VM Information
The VM that is created has the following default user accounts
 - root:vargrant
 - vagrant:vagrant
