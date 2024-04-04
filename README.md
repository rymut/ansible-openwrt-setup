# Ansible OpenWrt Setup

Repository shows how to use Ansible to configure OpenWrt.

## Required steps

Install required collections/roles from using ansible-galaxy

```bash
ansible-galaxy install -r requirements.yml
```

Under WSL it might be required to export variable `ANSIBLE_CONFIG` before running any playbook

```bash
export ANSIBLE_CONFIG=$PWD/ansible.cfg
```

## Usage

Test connection to router:

```bash
ansible -i inventories/inventory.yml -m ping router.home.arpa --ask-pass
```

Running setup script:

```bash
 ansible-playbook -i inventories/inventory.yml setup.yml -e name=router.home.arpa
```
