Vector-role
=========

Deliver log data to the ClickHouse database.

Requirements
------------

- OS Fedora 37 on managed nodes.

Role Variables
--------------

In defaults/main.yml :
- vector_version: "0.38.0" 
- clickhouse_ip: ""  - external ip of vm with clickhouse.

Templates
--------------

- vector.service.j2 - service vector configuration file.
- vector.toml.j2    - vector configuration file.

Dependencies
------------

Role required for full-time work:
- [Clickhouse](https://github.com/AlexeySetevoi/ansible-clickhouse.git)

Example Playbook
----------------

Install role :

- Create file ```requirements.yml``` with:
```yaml
- src: git@github.com:reocoker85/vector-role.git      
  scm: git
  version: "main"
  name: vector-role
```
- use command ```ansible-galaxy install -r requirements.yml -p roles``` for downloading role in directory roles.

Use role ( playbook example):

```yaml
- name: Install lighthouse
  hosts: vector
  become: true
  roles:
    - vector-role
  tags: vector
```

Author Information
------------------

### KIG
