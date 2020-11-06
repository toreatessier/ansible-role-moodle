# Ansible Role : Moodle

Ansible Role for Jakarta Project's moodle.

This roles configures Jakarta's moodle through different steps :
- [Git clones moodle 3.6 stable](https://github.com/moodle/moodle/tree/MOODLE_36_STABLE)
- Installs it
- Installs apache2 + PHP
- Configures apache2 + PHP
- Configures moodle

Requirements
------------

- VirtualBox

Example Playbook
----------------

```
- name: Deploy Moodle for Jakarta
  hosts: "{{ hosts }}"
  remote_user: "{{ user }}"
  tasks:
  - import_role:
      name: moodle
      tasks_from: install
    vars:
      vm_ip: "{{ moodle_ip }}"
      vm_name: jakarta_moodle
      vm_memory: "{{ moodle_ram }}"
```

Author Information
------------------

* **Toréa TESSIER** - <torea.tessier@reseau.eseo.fr> - [Jakarta Project](https://192.168.4.16/Equipe_1_Jakarta/)