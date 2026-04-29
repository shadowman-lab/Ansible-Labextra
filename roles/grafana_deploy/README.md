<!-- This was created with Claude Code -->

grafana_deploy
==============

An Ansible role for grafana deploy.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **grafana_user**: defaults file for ansible-grafana
  - Default: `grafana`

* **grafana_group**: Group name or identifier
  - Default: `grafana`

* **grafana_service_name**: Service name
  - Default: `grafana-server`

* **grafana_path_config**: Variable used in: Ensure Grafana config file is present
  - Default: `/etc/grafana`

* **grafana_path_logs**: File system path
  - Default: `/var/log/grafana`

* **grafana_path_data**: File system path
  - Default: `/var/lib/grafana`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: grafana_deploy
      vars:
        grafana_user: <value>
        grafana_group: <value>
        grafana_service_name: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
