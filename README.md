# Lamp-stack-ubuntu
Installing LAMP Stack on Ubuntu using Ansible playbook

```

---
- name: "Installing Httpd And Hosting A Site"
  hosts: all
  become: true
  tasks:
    
    - name: "LAMP - Package Installation"
      apt:
        name:
          - apache2
          - php
          - php-mysql
          - mysql-server
        state: present
          
    - name: "LAMP - httpd Service Restarting"
      service:
        name: apache2
        state: restarted
        enabled: true
          
    - name: "LAMP - mariadb Service Restarting"
      service:
        name: mysql
        state: restarted
        enabled: true
