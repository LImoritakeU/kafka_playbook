# KAFKA_CLUSTER DEPLOYMENT PLAYBOOK

This playbook is used to deploy kafka cluster at offline environment.

## Usage

- Global Variables should set in `group_vars/all.yml`
- Zookeeper Variables should set in `group_vars/zookeeper.yml`
- kafka Variables should set in `group_vars/kafka.yml`


```
# virtualenv will be suggested.

pip install -r requirements.txt
ansible-playbook site.yml --become
```

## Todo

- online and offline environent
