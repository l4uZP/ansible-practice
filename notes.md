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