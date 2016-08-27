# Provision.user
[![Galaxy](https://img.shields.io/badge/galaxy-provision.user-blue.svg?style=flat-square)](https://galaxy.ansible.com/khusnetdinov/provision.user/)

This is ansible receipt for creating deploy user for linux (Ubuntu). It also is used in other [provision receipt](https://github.com/khusnetdinov/provisioner) for prepare production enviroment on server.

It creates user, copies SSH key, sets nopasswd permissions. 

#### Variables

```yaml
user: deploy             # The name of deploy user 
home: '/home/{{ user }}'  # The home folder for user
```

#### Usage

Add `provision.user` to your roles and set vars in your vars file or playbook file.

requirements file:

```yaml
- src: "https://github.com/areceipt/provision.user"
  name: user
```

vars_file:

```yaml
deploy_user: deploy
deploy_user_home: "/home/{{ deploy_user }}"
```

playbook:

```yaml
- hosts: all
  roles:
    - role: user
      user: "{{ deploy_user }}"
      home: "{{ deploy_user_home }}"
```
