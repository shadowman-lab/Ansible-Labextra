<!-- This was created with Claude Code -->

jenkins_setup
=============

An Ansible role for jenkins setup.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **jenkins_url**: Variable used in: {{ jenkins_job_name }}
  - Default: `https://cicd.shadowman.dev:8083`

* **jenkins_job_name**: Variable used in: Create a jenkins job using basic authentication
  - Default: `Shadowman`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: jenkins_setup
      vars:
        jenkins_url: <value>
        jenkins_job_name: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
