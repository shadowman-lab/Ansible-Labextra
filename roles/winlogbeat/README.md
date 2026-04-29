<!-- This was created with Claude Code -->

winlogbeat
==========

An Ansible role for winlogbeat.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **winlogbeat_download_url_base**: Variable used in: Get winlogbeat zip
  - Default: `https://artifacts.elastic.co/downloads/beats/winlogbeat`

* **file_ext**: Variable used in: Get winlogbeat zip
  - Default: `.zip`

* **winlogbeat_download_file**: Variable used in: Get winlogbeat zip
  - Default: `winlogbeat-8.10.3-windows-x86_64`

* **winlogbeat_install_location**: Variable used in: Remove any previous winlogbeat
  - Default: `C:/Program Files/Winlogbeat`

* **kafkahost**: Target host or hostname
  - Default: `192.168.89.155:9092`

* **kafkatopic**: Destination location
  - Default: `windowslogs`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: winlogbeat
      vars:
        winlogbeat_download_url_base: <value>
        file_ext: <value>
        winlogbeat_download_file: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
