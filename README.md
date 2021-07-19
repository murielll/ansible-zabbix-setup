# Ansible playbook for distributed Zabbix 5.2 setup

Tested OS:
 - Ubuntu 20.04
 - CentOS 8

PostgreSQL version: 13


## Install Ansible requirements:

ansible-galaxy collection install community.postgresql

ansible-galaxy collection install community.general


## Configuration

Edit hosts.yml to correspond your needs.

Edit group_vars/all.yml to correspond your needs.

Create vault:

```
ansible-vault create vault.yml
```

Vault content must be like this:
```
zbx_db_pass: SuperStrongPass
```

Save vault password in file ```vault_password_file```

## Run playbook:

ansible-playbook -i hosts.yml -e @vault.yml --vault-password-file vault_password_file zabbix-pgsql-playbook.yml


