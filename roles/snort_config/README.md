<!-- This was created with Claude Code -->

snort_config
============

An Ansible role for snort config.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **ids_provider**: Unique identifier
  - Default: `snort`

* **ids_provider_list**: List of items
  - Default: `['snort']`

* **ids_config_remote_log_valid_protocols**: Log file path or logging configuration
  - Default: `['udp', 'tcp']`

* **ids_config_remote_log**: Variable used in: Enable remote logging
  - Default: `False`

* **ids_config_snort_version**: Version number or identifier
  - Default: `2.9.13`

* **ids_install_normalize_logs**: Log file path or logging configuration
  - Default: `False`

* **ids_config_snort_rules_dir**: Variable used in: Find snort rules
  - Default: `/etc/snort/rules/`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: snort_config
      vars:
        ids_provider: <value>
        ids_provider_list: <value>
        ids_config_remote_log_valid_protocols: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
