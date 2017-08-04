NginX
=========

Re-usable role for configuring Nginx. (Pronounced Engine-X)

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

    nginx_domain_name: yoursite

SSL
-------------

If you're deploying nginx with https, you'll want to set these variables.

    nginx_ports:
      - 80
      - "[::]:80"
      - 443 default ssl

     nginx_ssl: yes
     nginx_force_https: yes

The role will look for a local file and place it into /etc/ssl for you.

     nginx_ssl_cert: yoursite.crt
     nginx_ssl_key: yoursite.key

If you don't want to deploy a file, but used one already on the
remote's file system, you can use these variables instead.

    nginx_ssl_cert_path: /etc/ssl/certs/yoursite.crt
    nginx_ssl_key_path: /etc/ssl/private/yoursite.key


Reverse Proxy
-------------
This configuration defaults to using uwsgi_pass as its upstream component.  If
you want to use another component, you can do so with settings.

    nginx_upstream_pass: proxy_pass
    nginx_socket: http://localhost:8000

License
-------

BSD

Author Information
------------------

[Dan Cohen](https://www.dancohen.io)
