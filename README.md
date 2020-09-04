# ansible-ezmeral
Ansible playbooks for HPE Ezmeral Container Platform

## Prerequisites
- Download Ezmeral Container Platform binaries (install and prechecks scripts) in **bin** directory
- Create certificates for controllers and gateways in **certs** directory

### Install ansible
https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-centos-7

### How To Create an SSL Certificate on Apache for CentOS 7
https://www.digitalocean.com/community/tutorials/how-to-create-an-ssl-certificate-on-apache-for-centos-7
https://devcenter.heroku.com/articles/ssl-certificate-self

## Install controller
`ansible-playbook 01-install-controller.yml`
