# Useful commands

## Table of Contents
1. [Execution](#execution)
2. [Utilities](#utilities)

## Execution

### Run playbook
```shell
ansible-playbook -i inventory.yaml playbook.yaml
```

With vault values:
```shell
ansible-playbook -i inventory.yaml playbook.yaml --ask-vault-pass
```

## Utilities

### Ping all instances in the inventory
```shell
ansible all -m ping
```

### Use Ansible Vault to store sensitive values

#### Create new vault
```shell
ansible-vault create ./group_vars/all/vault
```

#### Edit existing vault
```shell
ansible-vault edit ./group_vars/all/vault
```

#### View existing vault
```shell
ansible-vault view ./group_vars/all/vault
```

### Debug and check variables
```shell
ansible -m debug -a 'var=hostvars[inventory_hostname]' -i ./inventory.yaml all
```