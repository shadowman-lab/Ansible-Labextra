<!-- This was created with Claude Code -->

elk_build
=========

An Ansible role for elk build.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **elk_cluster_name**: Resource name
  - Default: `elk-demo`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: elk_build
      vars:
        elk_cluster_name: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
