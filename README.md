# Ansible-VMWare-Spacewalk
Ansible based - auto deploy virtual machines through VMWare and Spacewalk netboot


----------

### Getting started
* Download all the *.yml files
* Please these in your playbook location
* You will need to edit your ansible hosts file - /etc/ansible/hosts

Add the following lines, if they do not exist
```
[vmware]
<vcenter-hostname>
```

```
[spacewalk-servers]
spacewalk ansible_ssh_host=<spacewalk-hostname>
[spacewalk-servers:vars]
ansible_user='<username>'
ansible_password='<password>'
ansible_become_pass='<password>'
```
The above is done with a sudo user, but you can amend your hosts file accordingly. This can also be done by using vault, however to keep this simple. Its just done with plain text. If you wish to use vault you will need to amend the playbooks accordingly.

The playbooks run in a cascade method, and therefore running the following command will execute them all. One after the other.

```
ansible-playbook deploy-linux-machine.yml
```

* Enjoy!

### Additional Information
If there is something which this script is missing, please feel free to let me know and I'll attempt to add it, or if you would like to contribute to this script. I am happy for you to do that too! 
I hope you find these playbooks of some use.
