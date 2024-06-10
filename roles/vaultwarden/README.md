Observer role
=========

We will run vaultwarden as docker container

Role Variables
--------------
vaultwarden_version: `string` the vaultwarden version
nginx_ssl_certificate_key: `string` certificate key path
nginx_ssl_csr: `string` certificate signing request path
nginx_ssl_certificate: `string` certificate path

smtp_host: `string` smtp host
smtp_from: `string` smtp from
smtp_port: `string` smtp server port
smtp_security: `string` smtp server port
auth_username: `string` username
auth_password: `string` password



Dependencies
------------
Docker

Notes
------------
Now playbook only support for Centos distribution
