# Packer Scripts
These scripts are used to Generate the Fedora 20 Base Box for Vagrant.

## Generate Fedora 20 Base Box for Vagrant
Follow the Steps below to Generate the Base Box.
 - Install Required Software
  - Install Packer v0.7.5 or Greater
  - Install VirtualBox v4.3.20 or Greater
 - Run `packer build -only=virtualbox-iso fedora-20-x86_64.json`
  - The Fedora ISO is upwards of 4gb in size and as a result may take awhile to download.
 - Packer will Launch a VirtualBox VM for the Installation. Do not Disturb it.
 - Completed build will be located at *../builds/virtualbox/jbemcop_fedora-21_base.box*

## Notes

### Download Progress stays at 0%
When downloading the Fedora 20 ISO, the download progress may stay at 0%. This is not a problem with the scripts or Packer, but a problem with the Fedora Server not returning a proper file size for the ISO. This can safely be ignored as the image will still be downloaded.
