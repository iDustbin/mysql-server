mysql-server
=========
![MySQL Server](https://upload.wikimedia.org/wikipedia/de/1/1f/Logo_MySQL.svg)
Format: ![Alt Text](url)

Install and setup mysql-server.

# Build Status
![Build Status](https://travis-ci.org/iDustbin/mysql-server.svg?branch=master "https://travis-ci.org/iDustbin/mysql-server/") | [mysql-server](https://travis-ci.org/iDustbin/mysql-server/)

# Donation
[![Donate Bitcoin](https://img.shields.io/badge/donate-€10-orange.svg)](http://example.com/donate-bitcoin/?amount=10&currency=EUR)

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

# Todo´s
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item