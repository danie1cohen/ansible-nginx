NGINX
=========

Re-usable role for configuring Nginx.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

If you're deploying nginx with https, you'll want to set these variables

    nginx_ports:
      - 80
      - "[::]:80"
      - 443 default ssl

     nginx_ssl: yes
     nginx_force_https: yes
     nginx_ssl_cert: /etc/ssl/certs/yoursite.crt
     nginx_ssl_key: /etc/ssl/private/yoursite.key

This configuration defaults to using uwsgi_pass as its upstream component.  If
you want to use another component, you can do so with settings.

    nginx_upstream_pass: proxy_pass
    nginx_upstream_prefix: http://



License
-------

BSD

Author Information
------------------

[Dan Cohen](https://www.dancohen.io)
