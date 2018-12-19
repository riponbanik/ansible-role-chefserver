Ansible Role to Install and Configure Openshource Chef Server 

[![Build Status](https://travis-ci.org/riponbanik/ansible-role-chefserver.svg?branch=master)](https://travis-ci.org/riponbanik/ansible-role-chefserver)

## Requirements

Your Chef server must have a resolvable hostname. The hostname for the Chef server must be a FQDN, including the domain suffix. se Ansible hostname module to change hostname to fqdn or use the following role variable to change hostname e.g.
   chefserver_hostname: chef.4thcoffee.com

When the install is successful, the server can be accessed using https://fqdn
     

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

   chefserver_version: 12.18.14

Specify the version of server to be installed.

  chefadmin_name: chefadmin
  chefadmin_email: admin@4thcoffee.com
  chefadmin_password: password
    
Console login credentials for default administrator. Not required if Management Console is not needed.

    chef_organization: 4thcoffee
    chef_organization_full_name: "Fourth Coffee, Inc."

Chef organization details.

    install_management_console: true

Install management console. Default true

    create_default_credential: true

Setup default administrator credential. Default true

## Dependencies

VM (on-perm or cloud) is needed to install. Tested with the following OS -

   1. Redhat Enterprise Linux 7
   2. CentOS 7
   3. Unbuntu 18.04 (Bionic) 
   4. Ubuntu 16.04 (Xenial)  

## Example Playbook

    - name: Install Puppet Master
      hosts: servers
      vars_files:
        - vars/main.yml
      roles:
        - role:  riponbanik.chefserver

## Installation

### Install the role from ansible galaxy to ansible default resarch path
```
sudo ansible-galaxy install riponbanik.chefserver -p /etc/ansible/roles
```

### Run the installation locally on the machine
```
sudo ansible-playbook -c local -i "localhost," playbook.yml
```

## License

MIT / BSD


## Author Information

This role was created in 2018 by [Ripon Banik](https://www.linkedin.com/in/ripon-banik-79956b23/)
