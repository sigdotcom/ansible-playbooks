# ansible-playbooks
Repository containing the various ansible-playbooks used for deployment.

For the Development site:
```ash
ansible-playbook -i inventories/development/hosts site.yml --ask-become-pass -v
```
