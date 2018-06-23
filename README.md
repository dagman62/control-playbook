# Ansible Playbook to Install nginx lb apache2 and MySQL

## If you plan on using Vagrant it requires vagrant-hostmanager plugin

```bash
vagrant plugin install vagrant-hostmanager
```
## If you dont use vagrant

If you are not behind dns you will have to add hosts to each node /etc/hosts

You will have to set the hosts up ssh passwordless

```bash
ssh-copy-id -i hostname 
```
Where hostname is each node done from the control host

## You should delete the vault file

```bash
./ansible/group_vars/vault
```
## From within ./ansible/group_vars create vault and export whatever editor you want

```bash
export EDITOR=vi
ansible-vault create vault
```
### Enter your own password and create the file with vi

```bash
---
vault_db_pass: MySecretPassword
```
###  You can enter the password at the command line or create a file

```bash
echo "MySecretPassword" > ./ansible/.vault_pass.txt
```
### This file is referenced in ./ansible/ansible.cfg

### change the permissions on .vault_pass.txt to 600

## Docker Instructions

### Run the following command

```bash
docker-compose build && docker-compose up -d
```

### After containers are up you will have to install ansible by hand

```bash
docker exec -it docker_control_1 /bin/bash
apt-get update
apt-get install -y software-properties-common
apt-add-repository ppa:ansible/ansible
apt-get update
apt-get install -y ansible
```
[Ansible Documentation](https://docs.ansible.com)