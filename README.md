# Ansible Role: NRPE Client

[![Build Status](https://travis-ci.org/networklore/ansible-role-nrpe-client.svg?branch=master)](https://travis-ci.org/networklore/ansible-role-nrpe-client)

This role installs the NRPE client on a monitoring server. You can use this role as an addon to the `networklore/nagios`role.


# Requirements

None.


# Role Variables

The variables you can configure are listed below. For the default settings you can look in `defaults/main.yml`.

    download_dir: /home/user/download/nrpe

This is the directory where the downloaded files will be placed and extracted.

    nrpeurl: http://sourceforge.net/projects/nagios/files/nrpe-2.x/nrpe-2.15/nrpe-2.15.tar.gz
    nrpesrc: nrpe-2.15

The download url for NRPE along with the directory name which will be created when the source file is
decompressed to. I.e. with `tar -xzvf nrpe-2.15.tar.gz`

    plugins_dir: /usr/local/nagios/libexec

The location of where you want to place the check_nrpe file, usually where your other monitoring plugins are located.

# Dependencies

This role doesn't have any strict dependencies but can be used with `networklore/nagios`.

# Example Playbook

Install NRPE to your current monitoring plugin directory.

    - hosts: monitoring-servers
      vars_files:
       - vars/main.yml    
      roles:
         - { role: networklore.nrpe-client }

*Contents of vars/main.yml*:

    plugins_dir: /usr/lib64/nagios/plugins

License
-------

BSD

Author Information
------------------

This role was created in 2016 by [Patrick Ogenstad](https://networklore.com).
