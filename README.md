mysql-server
=========

Install and setup mysql-server.

# Build Status
![Build Status](https://travis-ci.org/iDustbin/mysql-server.svg?branch=master "https://travis-ci.org/iDustbin/mysql-server/") | [mysql-server](https://travis-ci.org/iDustbin/mysql-server/)


# Example playbook

    - hosts: databases
      roles:
        - mysql-server
      vars:
        database_name: master
        mysql_server_bind_address: "{{ ansible_eth1.ipv4.address }}"
        mysql_server_root_password: <some-password>
        mysql_server_databases:
          - name: "{{ database_name }}"
            encoding: latin1
            collation: latin1_general_ci
        mysql_server_users:
          - name: webdev
            host: "%"
            password: <some-password>
            priv: "master.*:ALL"
