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
