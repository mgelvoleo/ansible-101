Demo on making user create a ssh, make user a sudoer and access the different server


```
ansible-playbook --ask-become-pass site.yml

```

```
ssh -i ~/.ssh/ansible mgelvoleo@server2
```
