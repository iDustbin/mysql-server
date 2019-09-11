mysql-server
=========
![MySQL Server](https://sqlbackupandftp.com/blog/wp-content/uploads/2018/11/logo-mysql-170x170.png)

Install Ansible Role for MySQL-Server 5.7 Community Edition

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

# Tested on
- [&#9745;] Debian - 6 - supported
- [&#9745;] Debian - 7 - supported
- [&#9745;] Debian - 8 - Jessie supported

- [&#9745;] Centos - 7.2 supported
- [&#9745;] Centos - 7.6 supported

- [&#9745;] RHEL - 7.6 supported
- [&#9745;] OL - 7.6 supported

# Todo´s
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item