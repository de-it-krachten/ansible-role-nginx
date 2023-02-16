[![CI](https://github.com/de-it-krachten/nginx/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/nginx/actions?query=workflow%3ACI)


# nginx

Install/configure/manage nginx



## Dependencies

#### Roles
None

#### Collections
- community.general
- ansible.posix

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 36
- Fedora 37

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Directory to put drop-in config files into
nginx_confd_path: /etc/nginx/conf.d

# Directory to put certificates & keys into
nginx_certs_path: /etc/nginx/certs

# list of drop-in config templates
nginx_confd_templates: []

# Create default server (port 80)
nginx_default_server: false

# should the firewall be managed by this role
nginx_manage_firewall: false

# Default firewall ports
nginx_fw_ports:
  - { port: 80, proto: tcp }
  - { port: 443, proto: tcp }

# Should vhosts be created
nginx_create_vhosts: true

# nginx service
nginx_service: nginx
</pre></code>


### vars/family-Debian.yml
<pre><code>
# nginx packages
nginx_packages:
  - nginx
  - python3-passlib

# Default private key location
nginx_ssl_key_path: /etc/ssl/private

# Default certificate location
nginx_ssl_crt_path: /etc/ssl/certs

# php socket
nginx_php_socket: /etc/alternatives/php-fpm.sock

# default nginx user/group
nginx_user: www-data
nginx_group: www-data
</pre></code>

### vars/family-RedHat-9.yml
<pre><code>
# nginx packages
nginx_packages:
  - nginx

# nginx pip packages
nginx_pip_packages:
  - passlib

# Default private key location
nginx_ssl_key_path: /etc/pki/tls/private

# Default certificate location
nginx_ssl_crt_path: /etc/pki/tls/certs

# default nginx user/group
nginx_user: nginx
nginx_group: nginx
</pre></code>

### vars/family-RedHat-8.yml
<pre><code>
# nginx packages
nginx_packages:
  - nginx
  - python3-passlib

# Default private key location
nginx_ssl_key_path: /etc/pki/tls/private

# Default certificate location
nginx_ssl_crt_path: /etc/pki/tls/certs

# default nginx user/group
nginx_user: nginx
nginx_group: nginx
</pre></code>

### vars/family-RedHat-7.yml
<pre><code>
# nginx packages
nginx_packages:
  - nginx
  - python-passlib

# Default private key location
nginx_ssl_key_path: /etc/pki/tls/private

# Default certificate location
nginx_ssl_crt_path: /etc/pki/tls/certs

# default nginx user/group
nginx_user: nginx
nginx_group: nginx
</pre></code>

### vars/Fedora.yml
<pre><code>
# nginx packages
nginx_packages:
  - nginx
  - python3-passlib

# Default private key location
nginx_ssl_key_path: /etc/pki/tls/private

# Default certificate location
nginx_ssl_crt_path: /etc/pki/tls/certs

# default nginx user/group
nginx_user: nginx
nginx_group: nginx
</pre></code>



## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'nginx'
  hosts: all
  become: "yes"
  vars:
    python_package_install_optional: True
    openssl_fqdn: server.example.com
    openssl_fqdn_additional: ['vhost1.example.com', 'vhost2.example.com']
    nginx_confd_templates: [{'server_name': 'test.example.com', 'template': 'templates/test.conf.j2', 'ssl_key': 'files/test.key', 'ssl_crt': 'files/test.crt', 'root': '/var/www/test.example.com/html', 'logdir': '/var/www/test.example.com/logs'}, {'name': 'www.example.com', 'server_name': ['www.example.com', 'foo.example.com'], 'template': 'templates/test.conf.j2', 'ssl_key': 'files/test.key', 'ssl_crt': 'files/test.crt', 'root': '/var/www/www.example.com/html'}]
  roles:
    - deitkrachten.showinfo
    - deitkrachten.python
    - deitkrachten.openssl
  tasks:
    - name: Include role 'nginx'
      ansible.builtin.include_role:
        name: nginx
</pre></code>
