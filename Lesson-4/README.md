---
- name: Example Ansible playbook for Handlers
  hosts: all
  become: yes
  remote_user: mgelvoleo
  

  environment:
    EXAMPLE: "Foo bar"

  tasks:
   - name: Environtment variable at Playbook Level
     ansible.builtin.command: "echo $EXAMPLE"

   - name: Environment var for only task level
     environment:
       EXAMPLE_LEVEL_VAR: "Hello VARIABLE"
     ansible.builtin.command: "echo $EXAMPLE_LEVEL_VAR"

   - name: Display both variable declare
     ansible.builtin.command: "echo $EXAMPLE EXAMPLE_LEVEL_VAR "
     

## RUN Playbook

```
ansible-playbook --inventory inventory/hosts ansible-env-variables-playbook.yml

```

