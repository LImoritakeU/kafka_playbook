# KAFKA_CLUSTER DEPLOYMENT PLAYBOOK

This playbook is used to deploy kafka cluster at offline environment.

## Requirement



## Usage

This playbook includes 3 roles:

1. common: firewalld, selinux...
2. zookeeper: install and deploy zookeeper cluster
3. kafka: install and deploy kafka cluster

## How to

### Install Ansible
```
# pip and virtualenv will be recommended.

pip install -r requirements.txt
```


### Setup IP Address, SSH Connection

in `hosts` file:
- Setup IP Address in `ansible_host` variable.
- Setup ssh username in `ansible_user` variable.
- Setup ssh password in `ansible_pass` variable
- Setup sudo password in `ansible_sudo_pass` variable.

** You can just ignore password options and use `-k` flag to input password in terminal by hand.


### Change Default Variables
- Global Variables should should be configured in `group_vars/all.yml`
- Zookeeper Variables should be configured in `group_vars/zookeeper.yml`
- kafka Variables should be configured in `group_vars/kafka.yml`


### Setup service-base Environment Variables
1. set `zk_register_path_env` and `kafka_register_path_env` variable value to **true**
2. set environment variable as `key: value` pair in `zk_env` and `kafka_env`.


### Execute Ansible Playbook
```
ansible-playbook site.yml --become [-k]
```

## Todo

- firewalld (DONE)
- common role
  - online and offline environent
- auto_numbering
- testing after setup

