# Ansible playbooks / Vagrant

This repo is for experimentation only.

## Vagrant commands

```bash
# destroy box
vagrant destroy

# create box from scratch and provision
vagrant up

# provision playbook changes
vagrant provision

# ssh into the box
vagrant ssh
```

## Ansible commands

```bash
# manually provision a Vagrant box
# http://docs.ansible.com/ansible/guide_vagrant.html
ansible-playbook --private-key=.vagrant/machines/[server]/virtualbox/private_key -u vagrant -i .vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory [playbook].yml
```

## Useful links & resources

##### Basic concepts
* https://adamcod.es/2014/09/23/vagrant-ansible-quickstart-tutorial.html

##### SysAdminCasts series
* https://sysadmincasts.com/episodes/43-19-minutes-with-ansible-part-1-4
* https://sysadmincasts.com/episodes/45-learning-ansible-with-vagrant-part-2-4
* https://sysadmincasts.com/episodes/46-configuration-management-with-ansible-part-3-4
* https://sysadmincasts.com/episodes/47-zero-downtime-deployments-with-ansible-part-4-4

##### Ansible documentation
* http://docs.ansible.com/ansible/guide_vagrant.html

##### Vagrant documentation
* https://www.vagrantup.com/docs/provisioning/ansible.html
