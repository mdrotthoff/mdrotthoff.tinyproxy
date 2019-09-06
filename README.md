## tinyproxy

[![Build Status](https://travis-ci.org/haad/ansible-tinyproxy.svg?branch=master)](https://travis-ci.org/haad/ansible-tinyproxy) [![Ansible Galaxy](https://galaxy.ansible.com/haad/tinyproxy)]

Set up (the latest version of) [Tinyproxy](https://tinyproxy.github.io/) on an Ubuntu systems.

#### Requirements

* `python-apt`

#### Variables

* `tinyproxy_log_level`: [default: `Info`] LogLevel to configure

* `tinyproxy_maxclients`: [default: `100`] Limit number of clients connected to Tinyproxy simultaneously
* `tinyproxy_minspare_servers`: [default: `5`] Minimum number of processes waiting for new users
* `tinyproxy_maxspare_servers`: [default: `10`] Maximum number of processes waiting for users
* `tinyproxy_startservers`: [default: `10`] Number of childs to start at begining
* `tinyproxy_maxrequest`: [default: `0`] Limit number of requests per client

* `tinyproxy_allowed_subnet`: [default: `0.0.0.0`] Subnets allowed to use proxy
* `tinyproxy_denied_subnet`: [default: `None`] Deny access from this subnet

* `tinyproxy_listen_address`: [default: `0.0.0.0`] IP address to bind to
* `tinyproxy_port`: [default: `8888`] Port for tinyproxy to listen on

* `tinyproxy_filtering`: Setup Tinyproxy filtering rules
  filter: "/etc/tinyproxy/filter"
  urls: On
  extended: On
  default_deny: Off
  case_sensitive: Off

* `tinyproxy_upstream_proxies`: [default: `[]`] List of upstream proxies to use
* `tinyproxy_upstream_proxies.{n}.address`: [required]: Address of upstream proxy in form host:port
* `tinyproxy_upstream_proxies.{n}.url`: [optional]: Optional URLs for which we want to use upstream proxy for.

#### TODO

* Make sure we can define multiple subnets to allow/deny