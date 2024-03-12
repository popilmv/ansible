# Ansible
Create default config:
```
ansible-config init --disabled -t all > ansible.cfg
```

Inventory = hosts: we can use IP here, add labels, create groups of VM, and attach vars to them like this:
```
[web]
IP
[web:vars]
ansible_user=root
```
In playbook, we describe all that we want to do on our VM. In this case, I describe what inventory I want and what roles will be used. 

Dir *roles* have apt and web. **apt** role just for updates before. ***web** will setup LAMP stack for Wordpress.
In **tasks** there is [main.yaml](https://github.com/popilmv/ansible/blob/main/roles/web/tasks/main.yaml) - here are my list of includes (tasks)
**Files** will be copy to my destination VM 
**handlers** like service ... restart

