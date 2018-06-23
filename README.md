# Ansible Playbook to Install nginx lb apache2 and MySQL

## If you plan on using Vagrant it requires vagrant-hostmanager plugin

```
vagrant plugin install vagrant-hostmanager
```
## If you dont use vagrant

If you are not behind dns you will have to add hosts to each node /etc/hosts

You will have to set the hosts up ssh passwordless

```
ssh-copy-id -i hostname 
```
Where hostname is each node done from the control host

## You should delete the vault file

```
./ansible/group_vars/vault
```
## Create your own from within that directory

```
export EDITOR=vi
ansible-vault create vault
```
### Enter your own password and create the file with vi

```
---
vault_db_pass: MySecretPassword
```
###  You can enter the password at the command line or create a file

```
echo "MySecretPassword" > ./ansible/.vault_pass.txt
```
### This file is referenced in ./ansible/ansible.cfg

### change the permissions on .vault_pass.txt to 600
