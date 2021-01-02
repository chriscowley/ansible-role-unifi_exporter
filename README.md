Unifi Exporter
=========

[![Actions Status](https://github.com/chriscowley/ansible-role-unifi_exporter/workflows/Static%20code%20analysis/badge.svg)](https://github.com/chriscowley/ansible-role-unifi_exporter/actions)
[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)
[![Ansible Role](https://img.shields.io/badge/ansible%20role-chriscowley.unifi_exporter-blue.svg)](https://galaxy.ansible.com/chriscowley/unifi_exporter)
![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/chriscowley/ansible-role-unifi_exporter)


Install and configure the [Unifi Prometheus Exporter](https://github.com/mdlayher/unifi_exporter)

Requirements
------------

- A Unifi Controller
- Prometheus

Role Variables
--------------

```
# defaults file for ccunix.unifi_exporter
unifi_exporter_version: 0.4.0
unifi_exporter_user: unifi_exporter
unifi_exporter_group: "{{ unifi_exporter_user }}"
unifi_exporter_home: "/var/lib/unifi_exporter"

unifi_exporter_address: :9130
unifi_exporter_metricspath: /metrics

unifi_exporter_unifi_address: https://localhost:8443
unifi_exporter_unifi_username: admin
unifi_exporter_unifi_password: changeme
unifi_exporter_unifi_site: home
unifi_exporter_unifi_insecure: false
```

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: unifi
      become: true
      
      roles:
        - role: ccunix.unifi_exporter
          state: present
      vars:
        unifi_exporter_unifi_address: https://localhost:8443
        unifi_exporter_unifi_username: admin
        unifi_exporter_unifi_password: "{{  vault_unifi_exporter_unifi_password }}"
        unifi_exporter_unifi_insecure: true

License
-------

MIT

Author Information
------------------

[Chris Cowley](https://github.com/chriscowley)
