### This is an example will be modified as per the requirements of our projects.

### Prerequisties
Installation of Ansible
server 

![Screenshot 2023-02-20 at 22-39-51 BVR_Apache2_all yml at master · ShortHills-Tech-Private-Limited_BVR_Apache2](https://user-images.githubusercontent.com/115537106/220266997-2a771721-6e91-4a12-922b-6b5f770d6549.png)

### run ansible playbook
ansible-playbook example.yml


(i). group_vars/all.yml: 
This is a file that contains variables that will be used in our playbook. In this example, we have two variables:

    apache_listen_port: The port that Apache2 will listen on (in this case, port 80).
    apache_server_admin: The email address of the server administrator (in this case, admin@example.com).
    
 ### (ii). playbook.yml: 
 This is the main playbook that will be run. It contains the following information:

    name: A description of what the playbook does (in this case, "Install and configure Apache").
    hosts: The hosts that the playbook will target (in this case, the web_servers group).
    become: A flag that tells Ansible to run commands as root using sudo.
    roles: The roles that will be applied to the hosts (in this case, the apache2 role).

### (iii). ansible.cfg: 
This is a configuration file that tells Ansible which inventory file to use and which remote user to connect as. In this example, we have specified the following:

    inventory: The location of the inventory file (./inventory/hosts.yml).
    remote_user: The user to connect as (ubuntu).

### (iv). roles/apache2/tasks/main.yml: 
This is the file that contains the tasks that will be run when the apache2 role is applied. Here is what each task does:

    Install the Apache2 package using the apt module.
    Configure Apache2 to listen on the port specified in apache_listen_port, using the lineinfile module to modify the ports.conf file.
    Configure the ServerAdmin directive in Apache2 using the lineinfile module to modify the servername.conf file.
    Enable the mod_rewrite and mod_ssl modules using the apache2_module module.
    Enable the default Apache2 site using the apache2_site module.

### (v). inventory/hosts.yml: 
This file contains the inventory, which specifies the hosts and groups that Ansible can target. In this example, we have two hosts (web1 and web2) in the web_servers group.

### (vi). inventory/host_vars/web1.yml and inventory/host_vars/web2.yml:
These files contain host-specific variables that will be used in our playbook. In this example, we have set the apache_server_name variable to a domain name for each host. 

In the Inventory/prod there is two files hosts & host_vars.

The hosts file within the prod directory would contain a list of hosts that belong to the prod environment.

The host_vars directory within the prod directory would contain YAML files with variables that are specific to each host in the prod environment.



