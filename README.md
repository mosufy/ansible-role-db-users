Ansible Role: DB Users
============================

This role will grant users access to database.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    mysql_root_password: "CCPQGcSV"

Set the database root password. This is required to add users.
    
    db_database: dbname
    db_username: dbusername
    db_password: dBP@ssw0rd

Set the default database name, username and password to grant access to.

    db_grant_users:
      - { database: "{{ db_database }}", username: "{{ db_username }}", host: localhost, password: "{{ db_password }}" }

This is where you will define the `database` to allow access to, the `username`@`host` and the user's `password`

Dependencies
------------

None.

Example Playbook
----------------

    - name: Grant user@host to database
      hosts: dbservers
      become: true
      become_method: sudo
      roles:
        - mosufy.db-users

License
-------

This codebase is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)

Author Information
------------------

For any issues with installation or getting this to work, send an email to: [mosufy@gmail.com](mailto:mosufy@gmail.com)
