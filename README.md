# Ansible Role: Clone an repo using PLESK API
Clones a git repo using [Plesk](https://docs.plesk.com/en-US/onyx/customer-guide/websites-and-domains/domains-and-dns/adding-subdomains.65180/).

## Requirements
No special requirements:
  * a server running plesk
  * this role requires admin access for plesk
  
## Role Variables
Required variables are listed below and can be set with values (see `vars/main.yml`):
```yaml
host_url: <your-strato-server-id>.stratoserver.net
host_port: 8443

domain_name: "mydomain.com"
subdomain_name: "my-new-instance"

plesk_admin_user: "admin"
plesk_admin_pw: "secure-admin-pw"

repo_name: "app"
remote_url: "https://github.com/itexia/ansible.role.create-subdomain-using-plesk-api.git"
```

## Dependencies
None.

## Example Playbook
```yaml
- hosts: strato-server
  become: yes
  vars_files:
    - vars/main.yml
  roles:
    - { role: ansible.ansible.role.clone-git-repo }
```
Inside `vars/main.yml`:
```yaml
host_url: <your-strato-server-id>.stratoserver.net
host_port: 8443

domain_name: "mydomain.com"
subdomain_name: "my-new-instance"

plesk_admin_user: "admin"
plesk_admin_pw: "secure-admin-pw"

repo_name: "app"
remote_url: "https://github.com/itexia/ansible.role.create-subdomain-using-plesk-api.git"
```

## Authors
This role was created in 2018 by Sergej Kukshausen and Susann Sgorzaly.

