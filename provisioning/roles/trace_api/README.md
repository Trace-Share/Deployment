# Ansible role trace_api

This role sets up Trace-API application with all dependencies.

Role installs following dependencies:
* PostgreSQL
* Python3
* NGNIX
* Docker


## Settings
All variables in this role are optional. Default values could be found [here](defaults/main.yml).

Role supports this variables:

##### PostgreSQL databse settings
* `postgre_username` - database username
* `postgre_password` - database password
* `postgre_database` - name of database

##### NGINX settings 
* `nginx_client_max_body_size` - max client upload size see [ngnix docs](http://nginx.org/en/docs/http/ngx_http_core_module.html#client_max_body_size)
