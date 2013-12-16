image-recipes
=============

This is a fork of [dtroyer/image-recipes](https://github.com/dtroyer/image-recipes)

Kickstart files and scripts for building minimal VM images.

How to
------
Here's the link about how-to on the author's blog. 
--> [A CentOS 6 Image for OpenStack](http://hackstack.org/x/blog/2013/04/25/a-centos-6-image-for-openstack/).

Requirements
------------
* Install virt-install and all its prerequisites
  * Ubuntu

    ```
    sudo apt-get install virtinst libguestfs-tools
    ```
  * CentOS

    ```
    sudo yum install libvirt python-virtinst qemu-kvm libguestfs-tools
    sudo /etc/init.d/libvirtd start
    ```

Features
--------

The images created will have the following features:
* minimal installs excluding the common 'base' groups
* timezone is UTC
* single root filesystem, grows to size of disk on first boot
* cloud-init is installed
* rng-tools is loaded to take advantage of host virt entropy if available
* build timestamp in /etc/.build

Fedora
------
* login name is 'fedora'

CentOS
------
* EPEL repo is enabled
* login name is 'centos'
* postfix is installed (prereq for cronie) but not enabled

Scientific Linux
----------------
* EPEL repo is enabled
* login name is 'sl-user'
