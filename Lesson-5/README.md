## Files under role/tasks main.yml

```
---
## Boolean Conditional check for installing Apache
- name: Install Apache web server
  apt:
    name: apache2
    state: absent
  when: install_apache_flag

## Putting multiple condition using ansible_facts
- name: Combine conditions using ansible facts
  debug:
    var: ansible_facts['kernel_version']
  when:
    - ansible_facts['os_family'] == "Debian"
    - ansible_facts['distribution_major_version'] == "20"

## Setting complex condition
- name: Setting complex condition
  debug:
    var: ansible_facts['kernel_version']
  when: ansible_facts['os_family'] == "Debian" and ansible_facts['distribution_major_version'] | int >= 20

## Register a variables and evaluate the value using when condition
- name: Register a variable
  ansible.builtin.command: cat /home/ubuntu/test-file.txt
  register: test_file_content

- name: Use the variable in conditional statement
  debug:
    var: test_file_content.stdout
  when: test_file_content.stdout.find('hi') != -1 #and test_file_content is succeeded

## When with Loop
- name: Run with items greater than 5
  ansible.builtin.command: echo {{ item }}
  loop: [ 0, 2, 4, 6, 8, 10 ]
  when: item > 5

## Conditionals based on ansible_facts
- name: How to use ansible_facts
  debug:
    var: ansible_facts['distribution']
    #var: ansible_facts['distribution_major_version']
    #var: ansible_facts['kernel_version']
    #var: ansible_facts
  when: ansible_facts['os_family'] == "Debian"
```


## Files under var/tasks main.yml

```
---
install_apache_flag: false
```



     

## RUN Playbook

```
ansible-playbook --inventory inventory/hosts ansible-conditional-playbook.yml

```

