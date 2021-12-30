# ansible-inventory-vagrant
The Dynamic Ansible inventory for Vagrant machines using Python 3.

Actually, there is no need for such dynamic inventory with Vagrant, as one can make use of the
[Ansible Provision](https://www.vagrantup.com/docs/provisioning/ansible) from Vagrant that is going to generate a
static inventory which itself is much faster than having to dynamically poll for the inventory.

This repo is just for archiving purposes here ;-) as it was copied from
[this gist](https://gist.github.com/lorin/4cae51e123b596d5c60d) and adapted for Python 3. The copied gist itself was
adapted from Mark Mandel's implementation which was on the Ansible core git repository.

In order to test this dynamic inventory make sure you have the requirements installed.

```bash
vagrant up # this also invokes the provisioner
pip3 install -r inventory/requirements.txt # install requirements for the Python script vagrant.py
ansible-inventory --list # make use of the dynamic inventory to list all hosts
ansible-playbook playbook.yml # invoke the playbook using ansible directly
vagrant provision # uses the static .vagrant/provisioners/ansible/inventory instead
```