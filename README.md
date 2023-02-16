### This Ansible_Skeleton will be modified as per the requirements of our projects.

## 1. Inventory:

This directory should contain one or more inventory files, which specify the hosts and groups of hosts that Ansible will manage.
Inventory files can be written in different formats such as INI and YAML

Example:  
![Screenshot from 2023-02-16 13-25-11](https://user-images.githubusercontent.com/115537106/219302581-0bf8a96a-04dc-4b2b-9f70-ed1cc27f51d9.png)![Screenshot from 2023-02-16 13-25-18](https://user-images.githubusercontent.com/115537106/219302601-30ebdc32-d0bf-451f-8740-d35aa3621e7b.png)

In the Inventory/prod there is two files hosts & host_vars.
The hosts file within the prod directory would contain a list of hosts that belong to the prod environment.

The host_vars directory within the prod directory would contain YAML files with variables that are specific to each host in the prod environment.


## 2. playbook.yml: 

This is the main playbook file that will be executed by Ansible. It will contain a series of tasks that will be executed on the hosts specified in the inventory.

## 3. roles:
This directory should contain one or more Ansible roles, which are collections of tasks, handlers, templates, and other files that can be reused across multiple playbooks.

### (i). files:  
This directory contains files that will be transferred to the remote host. These files are typically static files that are needed for the role to work, such as configuration files or scripts. 

### (iii). handlers:
This directory contains handlers that can be triggered by tasks within the role.

### (iv). tasks:
This directory contains the main tasks that the role performs. These tasks can be a combination of built-in Ansible modules and custom modules that you write yourself.

### (v). templates:
This directory contains templates that are used by the role to generate files that will be transferred to the remote host. These templates are typically Jinja2 templates that contain placeholders that will be filled in with variables at runtime. 

### (vi). vars:
This directory contains variables that are used by the role. These variables can be defined in YAML files or in Python files. 

## 4. group_vars/all.yml: 
This file contains variables that will be used across all hosts in the inventory.

## 5.ansible.cfg:
The ansible.cfg file is a configuration file for Ansible. It allows you to set default values for various settings such as the location of the inventory file, the default user for SSH connections, and many other settings


