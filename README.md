# Ansible Goodies

This repository contains Ansible playbooks and roles for common configuration setups, including LAMP and LEMP stacks, across multiple Linux distributions.

## Available Configurations

### LAMP Stack

The LAMP stack is a popular web development environment that includes Linux as the operating system, Apache as the web server, MySQL as the database server, and PHP as the programming language. Here is the [playbook](playbooks/lamp_stack.yml) and [role](roles/lamp/).

### LEMP Stack

The LEMP stack is similar to LAMP but replaces Apache with Nginx as the web server. It consists of Linux, Nginx, MySQL, and PHP. Here is the [playbook](playbooks/lemp_stack.yml) and [role](roles/lemp/).

## Requirements

- [X] Ansible
- [X] Vagrant
- [X] VirtualBox

## Usage (Manual)

To use the Ansible playbooks and roles in this repository, follow these steps:

1. Clone this repository:
```bash
git clone https://github.com/dmaax/ansible-goodies.git
```

2. Edit the production inventory file
```bash
vim inventory/production.ini
```

2. Run any playbook:
```bash
ansible-playbook -i inventory/production playbooks/lamp_stack
```

## Usage (Automated)

1. Clone this repository:
```bash
git clone https://github.com/dmaax/ansible-goodies.git
```

2. Edit [Vagrantfile](Vagrantfile) with the desired playbook
```bash
vim Vagrantfile
```

3. Bring the machine up
```bash
vagrant destroy -f; vagrant up
```