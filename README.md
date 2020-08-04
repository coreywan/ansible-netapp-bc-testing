# Netapp BC with Ansible

This repo is to show a simple version of a BC use case with Netapp.  This is not intended to walk you through a complex setup. For Consulting and guidance on a complex workflow, reach out to your WWT account team, and we can help provide that consultative service.


## Setup

1. Launch the [Netapp Ansible Automation Lab](https://www.wwt.com/lab/netapp-ansible-automation-lab) on the WWT Platform.  You will need to register an account before you are able to launch the lab.
2. Once launched, access the lab gateway through the lab provided. You should land on a jumphost with RHEL.
3. Open up Terminal, and run the following to get the jumphost ready
```sh
git clone git@github.com:coreywan/ansible-netapp-bc-testing.git
cd ansible-netapp-bc-testing
ansible-playbook setup_localhost.yml --vault-password-file ~/.vault_password -i inventory/ -vvv
exit
```
4. Open up a new Terminal. You should now have the virtual environment activated for you. Run the following to setup volumes and snapmirror relationships
```sh
ansible-playbook setup_netapp.yml --vault-password-file ~/.vault_password -i inventory
```
5. 