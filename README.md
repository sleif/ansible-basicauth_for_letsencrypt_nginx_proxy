sleif.basicauth_for_letsencrypt_nginx_proxy
============

This role adds basicauth to nginx based letsencrypt stack on docker.

Requirements
------------

Use it on a machine setup with ansible role sleif.docker.

Role Variables
--------------
- container_storage_dir_base (/srv)
- BASIC_AUTH_USER
 -BASIC_AUTH_PASSWD

Dependencies
------------

- geerlingguy.docker to make sure Docker is available.
- sleif.docker to make sure Docker is configured as needed.
- sleif.letsencrypt_nginx_docker

Example Playbook
----------------

    - hosts: "server"
      user: root
      vars:
        DOCKER_NETWORK_NAME: 'custom_docker_network'
        BASIC_AUTH_USER: admin
        BASIC_AUTH_PASSWD: password
      roles:
        - { role: sleif.basicauth_for_letsencrypt_nginx_proxy, tags: "basicauth_for_letsencrypt_nginx_proxy" }

License
-------

MIT

Author Information
------------------

Ulf Rompe
Sebastian Berthold
