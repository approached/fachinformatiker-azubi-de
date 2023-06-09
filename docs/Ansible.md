---
title: Ansible
---

# Ansible

Ansible ist eine Softlösung für das provisionieren ([Provisioning]).

## Code Snippets

Start a command:

    ansible testservers -i test -m "uptime" -k -vvvv -u root
    ansible testservers -i test -a "uptime" -k -u root

Task lineinfile:

    - name: set APP_DEBUG=false
      lineinfile: dest=/var/www/laravel/.env regexp='^APP_DEBUG=' line=APP_DEBUG=false

    - name: set APP_ENV=production
      lineinfile: dest=/var/www/laravel/.env regexp='^APP_ENV=' line=APP_ENV=production

Start playbook:

    ansible-playbook playbook-digitalocean.yml -i inventories/dev --private-key=/home/USER/.ssh/id_rsa -u root

Copy config:

    - name: Copy my .vimrc
      command: curl -LSso ~/.vimrc https://raw.github.com/ChengLong/configs/master/.vimrc
      sudo: no

## Links

-   [Ansible Project creator](https://phansible.com/)
