# ansible
Ansible is run using  
`ansible-playbook [filename].yml`  
  
Each playbook can be run on multiple or all hosts by putting them into a group  
Client nodes are added to a group in the `/etc/ansible/hosts` file

## docker.yml
Install's Jenkins through Docker on ansible-client-2  
Task's required to complete this job are listed in the yml file  

## git.yml
Install's the latest version of git on ansible-client-1  

## nexus.yml & nexus-distributions.yml
Install's nexus on ansible-client-3 using a git repository to run a script on the node  
nexus-distributions.yml adds an additional check for the distribution being used  
