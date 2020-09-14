# ansible-ezmeral
Ansible playbooks for HPE Ezmeral Container Platform

## Prerequisites
- Download Ezmeral Container Platform binaries (install and prechecks scripts) in **bin** directory  
`wget https://bluedata-releases.s3.amazonaws.com/5.1/hpe-cp-rhel-release-5.1-3011.bin`  
`wget https://bluedata-releases.s3.amazonaws.com/5.1/hpe-cp-prechecks-5.1.bin`  
- Create certificates for controllers and gateways in **certs** directory

### Install ansible
https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-centos-7

### How To Create an SSL Certificate on Apache for CentOS 7
https://www.digitalocean.com/community/tutorials/how-to-create-an-ssl-certificate-on-apache-for-centos-7  
https://devcenter.heroku.com/articles/ssl-certificate-self  
`openssl genrsa -des3 -passout pass:x -out ezmeral.pass.key 2048`  
`openssl rsa -passin pass:x -in ezmeral.pass.key -out controller.key`  
`openssl req -new -key controller.key -out controller.csr`  
`openssl x509 -req -sha256 -days 365 -in controller.csr -signkey controller.key -out controller.crt`  
`openssl rsa -passin pass:x -in ezmeral.pass.key -out gateway.key`  
`openssl req -new -key gateway.key -out gateway.csr`  
`openssl x509 -req -sha256 -days 365 -in gateway.csr -signkey gateway.key -out gateway.crt`  

## Install controller
`ansible-playbook 01-install-controller.yml`
