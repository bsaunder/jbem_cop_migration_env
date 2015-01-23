# JBEM CoP Standard Migration Environment
This repo contains the scripts and code necessary to build a standard development environment that can be used for migrating JBoss based applications.

## Environment Information
The default VM that is built and configured is a VirtualBox VM that can be run on any OS. The VM is built on Fedora 20 x64 and contains the following software packages:
 - Update
 - As
 - Provisioned

## Running the Environment
Follow the steps below to build the Environment
  - Install the Required Software
    - [Packer v0.7.5 or Greater](https://packer.io/downloads.html)
    - [VirtualBox v4.3.20 or Greater](https://www.virtualbox.org/wiki/Downloads)
    - [Vagrant v1.7.2 or Greater](https://www.vagrantup.com/downloads.html)
  - Change to `packer` directory
  - Run `packer build -only=virtualbox-iso fedora-20-x86_64.json`
    - The Fedora ISO is upwards of 4gb in size and as a result may take awhile to download.
  - Packer will Launch a VirtualBox VM for the Installation. Do not Disturb it.
  - Completed build will be located at `builds/virtualbox/jbemcop_fedora-21_base.box`
  - Change to `vagrant` directory
  - Add the Vagrant Base image to Vagrant by running `vagrant box add jbemcop-fedora20-base ../builds/virtualbox/jbemcop_fedora-20_base.box`
  - Run `vagrant up` to Start VM

## Default VM Information
The VM that is created has the following default user accounts
 - root:vargrant
 - vagrant:vagrant

The following directories are shared by default with the VM
 - vagrant -> /vagrant
 - shared_data -> /shared_data
  - It is recommended that any user data that needs to be shared is placed here

## Notes

### Download Progress stays at 0%
When downloading the Fedora 20 ISO, the download progress may stay at 0%. This is not a problem with the scripts or Packer, but a problem with the Fedora Server not returning a proper file size for the ISO. This can safely be ignored as the image will still be downloaded.
