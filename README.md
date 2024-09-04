# CONFIGURATION MANAGEMENT TOOLS - ANSIBLE

**Tools that helps in making os level changes with much more advanced features are tools considered under management tools**
1. CF Engine
2. Puppet
3. Chef
4. **Ansible**

   4.1. Ansible solves shell problems

   4.2. Declarative

   4.3 Heterogeneous by default

   4.4 Ansible can scale to large infrastructure 

Ansible supports both push and pull, we need to understand what works for us better and we need to chose one or both accordingly to our requirements.

**Ansible core vs ansible**
  
  Ansible developed by Michael till 2.10 it's ansible core v2.10
  After that redhat acquires ansible ansible and named as ansible 1, ansible 2 like that

**How ansible Managed the node**
  
  Ansible uses SSH
  Exp: ansible -i serverip1, ip2  all -m ping -e ansible_user=centos -e ansible_password=Devops321
      i : inventory 
  Check ansible inventory directory structure in Google

**How ansible connect to the node?**

  Uses ssh 
  
  Ansible needs inventory 

**How ansible Manages node configuration?**

  Earlier modules
  
  Now it's collection (collection is nothing but group of modules)


# Ansible playbook

**Whatever we want to do we have to kept that in playbook (list of collections)**

Ansible playbook to be written in YAML Markup Language 

Ansible uses markup language 

    eXtensible Markup Language (XML)
    
    Java Script Object Notation (Json)
    
    Yet Another Markup Language (YAML)

plain

List

Map/Dictionary

**XML**

We declare like
```
<key>Value</key>

<a>10</a>
```
**Json**
```
{

“a” = 10

}
```
**YAML**

in YAML we must maintain indentation 
```
a: 10

b: [99,89]

b:

- 99
- 89
```
Ansible is expecting the inputs in YAML

Keys(Parameters) are provided by ansible

Some values are also provided by ansible

**Sample Ansible playbook**

**playbook.yml or playbook.yaml**
```
- name: Some Playbook (Play1)
  hosts: all
  tasks:
    - name: Demo task
      ansible.builtin.yum:
        name: nginx
        state: installed
- name: Role Playbook (Play2)
  hosts: all
  roles:
    - Demo
```
playbook.yml or playbook.yaml is a playbook

Every Playbook starts with a list meaning it can have one or more plays.

name keyword on play level is optional and itsgood to have.

hosts is must to have keyword

either task or role is a must to have role.
