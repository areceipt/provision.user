# Provision.user
[![Galaxy](https://img.shields.io/badge/galaxy-provision.user-blue.svg?style=flat-square)](https://galaxy.ansible.com/khusnetdinov/provision.user/)

This receipt creates `user` for deployment and managing operations on Ubuntu server.

## What it does?

 Under root user it:
 
 * Creates user
 
 * Gets ssh key from local machine and puts to server user authorized_keys
 
 * Grant user sudo without password permissions
 
 * Restrict password login, allow only SSH connection
 
 * Restrict root login

## Files structure

```
├── /defaults/                  # Default variables for playbook
│   └── main.yml                # Variables for playbook
├── /meta/                      # Meta
│   └── main.yml                # Ansible Galaxy meta information
├── /tasks/                     # Play tasks
│   └── main.yml                # User provision task
│── README.md                   # Project description
│── hosts                       # Inventory file
└── playbook.yml                # Playbook file
```

## Usage

#### Set Variables

```yaml
  # defaults/main.yml
 
  # User name on remote server
  provision_user_name: deploy
  # SSH key file name on local machine
  provision_user_ssh_key: id_rsa
```

#### Set provision hosts

```ini
# hosts

[provision]
# Set you hosts
0.0.0.0
```

#### Run provision

```bash
$ ansible-playbook playbook.yml -i hosts -vvv
```
