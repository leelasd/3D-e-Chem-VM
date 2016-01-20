Scripts to create a Vagrant box using packer and ansible.

# Usage

* VirtualBox, https://www.virtualbox.org
* Vagrant, https://www.vagrantup.com

Start virtual machine with

```
vagrant init nlesc/3d-e-chem
vagrant up
```

# Build

Requirements:

* Virtualbox, https://www.virtualbox.org/
* Vagrant, https://www.vagrantup.com/
* Packer, https://packer.io
* Atlas account, https://atlas.hashicorp.com
* Enough disk space
  * Make sure temporary directory (/tmp by default on Linux) has enough space. Use TMPDIR environment variable to overwrite default location
* OVF file (../Chemical-Analytics-Platform/output-virtualbox-iso/*.ovf) from build phase of https://github.com/NLeSC/Chemical-Analytics-Platform

```
packer build packer.json
```
# Test

Add box to Vagrant with

```
vagrant box add --name nlesc/3d-e-chem --force packer_virtualbox-iso_virtualbox.box
```

Then use steps described at Usage chapter in a new directory.
