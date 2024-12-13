## RUN Playbook

```
ansible-playbook --inventory inventory/hosts ansible-variables-playbook.yml

```

## Run playbook with run time variables
```
ansible-playbook --inventory inventory/hosts ansible-variables-playbook.yml --extra-vars '{"version":"1.0","other_variable":"foo-world"}' 
```


## Run playbook with vars from YAML file
```
ansible-playbook --inventory inventory/hosts ansible-variables-playbook.yml --extra-vars "@my-vars.yml"
```


## ## RUN playb book with tags
```
ansible-playbook --inventory inventory/hosts ansible-variables-playbook.yml --tags string_var
```