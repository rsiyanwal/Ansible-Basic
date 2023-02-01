# Ansible-Basic
Basic ansible

```
---
- name: Example Ansible Playbook
  hosts: localhost
  tasks:
    - name: Install the Apache web server
      become: yes
      apt:
        name: apache2
        state: present
    - name: Start the Apache web server
      become: yes
      service:
        name: apache2
        state: started
        enabled: yes
```

In this example, we have a playbook with two tasks. The first task installs the Apache web server by using the apt module, which manages packages on Debian-based systems. The name attribute specifies the name of the package to install, in this case apache2, and the state attribute specifies that the package should be installed if it is not already present. The become attribute is used to run the task as an administrator (root), allowing us to install the package.

The second task starts the Apache web server by using the service module, which manages services on Linux systems. The name attribute specifies the name of the service to manage, in this case apache2, the state attribute specifies that the service should be started, and the enabled attribute specifies that the service should be started automatically when the system boots. Again, the become attribute is used to run the task as an administrator.

To run this playbook, you would save the script in a file with a .yml extension and then run the ansible-playbook command, passing the name of the file as an argument. For example:

```
ansible-playbook example.yml
```
