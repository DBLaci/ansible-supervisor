## supervisor

[![Build Status](https://travis-ci.org/Oefenweb/ansible-supervisor.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-supervisor) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-supervisor-blue.svg)](https://galaxy.ansible.com/list#/roles/3238)

Set up the latest or a specific version of supervisor in Ubuntu systems.

#### Requirements

* `python-dev` (will be installed)
* `python-pip` (will be installed)

#### Variables

* `supervisor_version` [default: `3.1.3`]: Supervisor version lto install (e.g. `latest`, `3.1.3`)

* `supervisor_unix_http_server_file` [default: `/var/run/supervisor.sock`]: A path to a UNIX domain socket (e.g. /tmp/supervisord.sock) on which supervisor will listen for HTTP/XML-RPC requests. `supervisorctl` uses XML-RPC to communicate with supervisord over this port
* `supervisor_unix_http_server_chmod` [default: `'0700'`]: Change the UNIX permission mode bits of the UNIX domain socket to this value at startup

* `supervisor_inet_http_server_enabled` [default: `false`]: Whether or not to enable the HTTP server
* `supervisor_inet_http_server_port` [default: `9001`]: A TCP host:port value or (e.g. `127.0.0.1:9001`) on which supervisor will listen for HTTP/XML-RPC requests. `supervisorctl` will use XML-RPC to communicate with supervisord over this port
* `supervisor_inet_http_server_username` [default: `admin`]: The username required for authentication to this HTTP server **Make sure to change!**
* `supervisor_inet_http_server_password` [default: `'4ubA&Et=ASPe'`]: The password required for authentication to this HTTP server. This can be a cleartext password, or can be specified as a SHA-1 hash if prefixed by the string `{SHA}` **Make sure to change!**

* `supervisor_supervisord_logfile` [default: `/var/log/supervisor/supervisord.log`]: The path to the activity log of the supervisord process
* `supervisor_supervisord_pidfile` [default: `/var/run/supervisord.pid`]: The location in which supervisord keeps its pid file
* `supervisor_supervisord_childlogdir` [default: `/var/log/supervisor`]: The directory used for `AUTO` child log files

* `supervisor_supervisorctl_serverurl` [default: `"unix://{{ supervisor_unix_http_server_file }}"`]: The URL that should be used to access the supervisord server, e.g. `http://localhost:9001`. For UNIX domain sockets, use `unix:///absolute/path/to/file.sock`

* `supervisor_include` [default: `'/etc/supervisor/conf.d/*.conf'`]: A (single) absolute file glob of files to include

## Dependencies

None

#### Example

```yaml
---
- hosts: all
  roles:
  - supervisor
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-supervisor/issues)!