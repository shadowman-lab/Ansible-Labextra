<!-- This was created with Claude Code -->

auditbeat
=========

An Ansible role for auditbeat.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **auditbeat_download_url_base**: URL or URI endpoint
  - Default: `https://artifacts.elastic.co/downloads/beats/auditbeat`

* **file_ext**: Configuration parameter for auditbeat
  - Default: `.zip`

* **rhelfile_ext**: Configuration parameter for auditbeat
  - Default: `.rpm`

* **auditbeat_download_file**: Configuration parameter for auditbeat
  - Default: `auditbeat-8.17.1-windows-x86_64`

* **rhelauditbeat_download_file**: Configuration parameter for auditbeat
  - Default: `auditbeat-8.17.1-x86_64`

* **auditbeat_install_location**: Installation flag or package name
  - Default: `C:/Program Files/Auditbeat`

* **kafkahost**: Target host or hostname
  - Default: `172.16.2.216:9092`

* **kafkatopic**: Destination location
  - Default: `auditbeat`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: auditbeat
      vars:
        auditbeat_download_url_base: <value>
        file_ext: <value>
        rhelfile_ext: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
