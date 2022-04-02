[![CI](https://github.com/de-it-krachten/ansible-role-nginx/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-nginx/actions?query=workflow%3ACI)


# ansible-role-nginx

Install/configure/manage nginx


Platforms
--------------

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- CentOS 7
- RockyLinux 8
- AlmaLinux 8<sup>1</sup>
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms

Role Variables
--------------
<pre><code>
# Directory to put drop-in config files into
nginx_confd_path: /etc/nginx/conf.d

# list of drop-in config templates
nginx_confd_templates: []
</pre></code>


Example Playbook
----------------

<pre><code>
- name: sample playbook for role 'nginx'
  hosts: all
  vars:
    nginx_confd_templates: [{'server_name': 'test.example.com', 'template': 'templates/test.conf.j2', 'ssl_key': 'files/test.key', 'ssl_crt': 'files/test.crt'}]
  tasks:
    - name: Include role 'nginx'
      include_role:
        name: nginx
</pre></code>
