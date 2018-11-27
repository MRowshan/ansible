# ansible
Ansible is run using  
`ansible-playbook [filename].yml`  
  
Each playbook can be run on multiple or all hosts by putting them into a group  
Client nodes are added to a group in the `/etc/ansible/hosts` file  

An example of what is added to the `/etc/ansible/hosts` file: `user@ip-address` or `user@vm-name`  
eg. `terraform@ansible-client-1` 

Groups can be added in the `/etc/ansible/hosts` file using: `[group-name]`

## docker.yml
Install's Jenkins through Docker on ansible-client-2  
Task's required to complete this job are listed in the yml file  

## git.yml
Install's the latest version of git on ansible-client-1  

## nexus.yml
Install's nexus on ansible-client-3 using a git repository to run a script on the node  

## nexus-distributions.yml
nexus-distributions.yml adds an additional check for the distribution being used  
In this case, Ubuntu is being used. Ubuntu comes with python3 default, and ansible needs to be pointed to the binary.   
To do this, edit the `/etc/ansible/hosts` file with the following:  
```
[ubuntu-hosts]
user@vm-name/ip-address
[ubuntu_hosts:vars]
ansible_python_interpreter = /usr/bin/python3
```
### apt.yml & yum.yml
import_tasks uses the relevant yml file based on the OS used on the client machine
