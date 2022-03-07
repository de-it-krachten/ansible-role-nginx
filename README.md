[![CI](https://github.com/de-it-krachten/ansible-role-nginx/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-nginx/actions?query=workflow%3ACI)


# ansible-role-nginx

Install/configure/manage nginx


Platforms
--------------

Supported platforms

- CentOS 7
- RockyLinux 8
- AlmaLinux 8
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Fedora 34



Role Variables
--------------
<pre><code>
# Nginx packages 
nginx_packages:
  - nginx

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
    nginx_ssl_key: files/test.key
    nginx_ssl_crt: files/test.crt
    nginx_confd_templates: ['templates/test.conf.j2']
  pre_tasks:

    - name: Install openssl
      package:
        name: openssl
        state: present
 
    - name: Create private key
      openssl_privatekey:
        path: "{{ playbook_dir }}/files/test.key"
        size: 2048
      become: no
      delegate_to: localhost

    - name: Create CSR
      openssl_csr:
        path: "{{ playbook_dir }}/files/test.csr"
        privatekey_path: "{{ playbook_dir }}/files/test.key"
      become: no
      delegate_to: localhost

    - name: Perform a self-sign of the certificate
      openssl_certificate:
        provider: selfsigned
        path: "{{ playbook_dir }}/files/test.crt"
        privatekey_path: "{{ playbook_dir }}/files/test.key"
        csr_path: "{{ playbook_dir }}/files/test.csr"
      become: no
      delegate_to: localhost

  tasks:
    - name: Include role 'nginx'
      include_role:
        name: nginx
</pre></code>
