INFRASTRUCTURE - DEPLOY
-----------------------

####Ansible playbook
Application Deployment + Server configuration
- Works for debian 8 instance in OVH
- Ansible roles: Geerlingguy [GitHub](https://github.com/geerlingguy)
  - [geerlingguy.dotdeb](https://github.com/geerlingguy/ansible-role-repo-dotdeb) (import php7)
  - [geerlingguy.apache](https://github.com/geerlingguy/ansible-role-apache/)
  - [geerlingguy.firewall](https://github.com/geerlingguy/ansible-role-firewall)
  - [geerlingguy.php](https://github.com/geerlingguy/ansible-role-php)

####Vagrantfile
- Debian 8 / Jessie 64

####Info
Roles not imported with ansible-galaxy directly. Some packages were added

Ip: 192.168.69.69