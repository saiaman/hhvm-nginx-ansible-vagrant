hhvm-nginx-ansible-vagrant
==========================

HHVM Nginx Ansible Vagrant Solution - This will spin up a EC2 t1.micro instace in AWS

Requirements
============

Ansible >= 1.4
vagrant >= 1.4
vagrant-aws plugin (install using "vagrant install vagrantf-aws")
Ubuntu 12.04 LTS

Usage
=====

1. Change the group_var/all
2. Change the site.yml file
3. Change Vagrantfile and change following aws credentils

    aws.access_key_id=''
    aws.secret_access_key=''
    aws.keypair_name = ''
    override.ssh.private_key_path = ''
    aws.instance_type = "t1.micro"
    aws.security_groups = 'HHVM'
    aws.ami = "ami-3d128f07"
    override.ssh.username = 'ubuntu'
    aws.region = "ap-southeast-2"


4. Run "vagrant up --provider=aws"
5. Point your browser to DNS/inde.php and you will see "HipHop" message, which means HHVM running cleanly!
6. Enjoy

Author
======

nalindak

