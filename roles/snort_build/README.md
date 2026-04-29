<!-- This was created with Claude Code -->

snort_build
===========

An Ansible role for snort build.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **ids_provider**: Variable used in: Verify required variable is defined
  - Default: `snort`

* **ids_provider_list**: Variable used in: Ensure ids_provider is valid
  - Default: `['snort']`

* **ids_install_snort_barnyard2_normalize_logs**: Variable used in: Configure ids log normalization for provider snort
  - Default: `False`

* **ids_config_snort_version**: Version number or identifier
  - Default: `2.9.13`

* **ids_install_snort_interface**: Installation flag or package name
  - Default: `enp1s0`

* **ids_install_snort_user**: Username or user account name
  - Default: `root`

* **ids_install_snort_group**: Installation flag or package name
  - Default: `root`

* **ids_install_snort_pkgs**: Variable used in: Install snort and dependent packages - defaults
  - Default: `['https://s3.amazonaws.com/ansible-security.workshop-files/daq-2.0.6-1.el7.x86_64.rpm', 'https://s3.amazonaws.com/ansible-security.workshop-files/snort-2.9.13-1.centos7.x86_64.rpm', 'libdnet', 'rsyslog']`

* **ids_install_snort_barnyard_pkg**: Variable used in: Install barnyard
  - Default: `https://s3.amazonaws.com/ansible-security.workshop-files/barnyard2-1.13-1.el7.x86_64.rpm`

* **ids_install_snort_community_rules_url**: Variable used in: Handle ids_install_snort_community_rules_url
  - Default: `https://s3.amazonaws.com/ansible-security.workshop-files/community-rules.tar.gz`

* **ids_install_snort_registered_rules_url**: Variable used in: Handle ids_install_snort_registered_rules_url rules
  - Default: `https://s3.amazonaws.com/ansible-security.workshop-files/snortrules-snapshot-29130.tar.gz`

* **ids_install_normalize_logs**: Log file path or logging configuration
  - Default: `False`

* **ids_install_snort_community_rules_subdir**: Directory path
  - Default: `community-rules`

* **ids_install_snort_registered_rules_subdir**: Directory path
  - Default: `rules`

* **ids_install_snort_promiscuous_interface**: Installation flag or package name
  - Default: `False`

* **ids_install_snort_use_pulledpork**: Variable used in: pulledpork
  - Default: `False`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: snort_build
      vars:
        ids_provider: <value>
        ids_provider_list: <value>
        ids_install_snort_barnyard2_normalize_logs: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
