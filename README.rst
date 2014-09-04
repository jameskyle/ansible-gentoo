ansible-gentoo
==============

This role demonstrates the automatic configuration of a gentoo system from
minimal install to first boot.

Role Variables
--------------

The role defines several defaults that an be overridden by the user

pubkey
    The public key to deploy to the root user on the *minimal cd*. Primarily to
    negate the need for a password if you need to run twice.  
    default: ~/.ssh/id_rsa.pub

main_disk
    The target disk for the install.  
    default: /dev/sda

swap_size
    Size of the swap partition  
    default: 2048m

fstype
    filesystem type for root and boot drives  
    default: ext4

force_format
    Whether to force a reformat of a partition  
    default: no

mirror
    The mirror to fetch the gentoo stage3 sources from.  
    default: http://mirror.mcs.anl.gov/pub/gentoo 

timezone
    The timezone to set for the new system.  
    default: America/Los_Angeles

domain
    main domain for the new system  
    default: met.tfoundry.com

kernel
    The kernel configuration to use.  
    default: config-3.13.0-24-generic

make_opts
    any make options you wish to pass for ebuilds.  
    default: -j4

management_interface
    the main interface to configure  
    default: ansible_default_ipv4.interface

root_passwd
    the initial root password for the newly installed system.  
    default: gentoo-root

gateway
    the default gateway for the newly installed system.  
    default: ansible_default_ipv4.gateway

netmask
    the netmask for the newly installed system  
    default: ansible_default_ipv4.netmask


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables 
passed in as parameters) is always nice for users too:

.. code:: yaml 

    - hosts: all
      roles:
         - gentoo

Also please see  `blog post`_  for an example of using this role to deploy 
gentoo.

License
-------

BSD

Author Information
------------------

James A. Kyle  
james@jameskyle.org  
http://blog.jameskyle.org

.. _`blog post`: http://blog.jameskyle.org/2014/08/automated-stage3-gentoo-install-using-ansible/
