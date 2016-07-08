# RIDING BYTES: PostgreSQL Role

This role provisions [PostgreSQL][9].

This role istalls [PostgreSQL][9] using the [PostgreSQL Ansible Role][10] and
configure it in secure ways.

## Dependencies

This role depends on the follwoing [Ansible Roles][5]:

- [PostgreSQL][10]


## PostgreSQL Variables

Please refer to the [PostgreSQL Ansible Role][10] for available variables.
This role customizes the following variables in `vars/main.yml`:

    postgresql_version: 9.5

Install [PostgreSQL][9] version 9.5 per default.

    postgresql_pg_hba_default:
      - type: local
        database: all
        user: '{{ postgresql_admin_user }}'
        address: ''
        method: 'peer'
        comment: ''
      - type: local
        database: all
        user: all
        address: ''
        method: 'peer'
        comment: '"local" is for Unix domain socket connections only'

Only allow local connections to the Unix-domain socket uainf `peer` authentication.
Please see [PostgreSQL Host Based Authentication Documentation][11] for available settings.


[1]:  http://ridingbytes.com "RIDING BYTES"
[2]:  https://www.vagrantup.com/docs/getting-started/ "Vagrant"
[3]:  https://www.ansible.com "Ansible"
[4]:  https://docs.ansible.com/ansible/playbooks.html "Ansible Playbook"
[5]:  https://docs.ansible.com/ansible/playbooks_roles.html "Ansible Roles"
[6]:  https://galaxy.ansible.com "Ansible Galaxy"
[7]:  https://docs.ansible.com/ansible/intro_inventory.html "Ansible Inventory"
[8]:  https://www.postgresql.org "PostgreSQL"
[9]:  https://galaxy.ansible.com/ANXS/postgresql "PostgreSQL Ansible Role"
[10]: https://www.postgresql.org/docs/9.5/static/auth-pg-hba-conf.html "PostgreSQL HBA"
