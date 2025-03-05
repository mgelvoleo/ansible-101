Usage:
Deploy to Blue Environment:

```
ansible-playbook playbook.yml -e target_group=blue
```

Deploy to Green Environment:
```
ansible-playbook playbook.yml -e target_group=green
```

Switch Traffic (would typically involve load balancer config update):

```
# Example using HAProxy (additional playbook needed)
ansible-playbook switch-traffic.yml -e active_group=green
```