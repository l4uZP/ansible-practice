## Ad-hoc commands

**Testing ping**
``` bash
ansible all -i inventory -m ansible.builtin.ping
```

**Running shell commands**
``` bash
ansible all -i inventory -m ansible.builtin.shell -a "date"
```

**Installing a package**
```bash
ansible webservers -i inventory -m ansible.builtin.package -a "name=htop state=present" -b -K
```

## Playbooks

**Running a playbook**
``` bash
ansible-playbook -i inventory example-playbook.yml
```
**Running a playbook that needs password**
``` bash
ansible-playbook -i inventory testing-modules.yml --ask-become-pass
```
**Running a playbook that needs to become root**
```bash
ansible-playbook -i inventory nginx-playbook.yml --become -K
```

### Modules

**file:** Create, delete or modify files and directories
**copy:** Copy files from control node to managed machines
**service:** Ensure the status of a selected service 

### Variables, facts and templates

To see what facts ansible collects:
```bash
ansible all -i inventory -m setup
```
