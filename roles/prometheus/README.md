<!-- This was created with Claude Code -->

prometheus
==========

An Ansible role for prometheus.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **prometheus_group**: Prometheus system user group
  - Default: `prometheus`

* **prometheus_user**: Prometheus system user name
  - Default: `prometheus`

* **prometheus_path_install**: Prometheus install path
  - Default: `/usr/local/bin/prometheustools`

* **prometheus_path_config**: Prometheus configuration path
  - Default: `/etc/prometheus`

* **prometheus_config_dir**: Directory path
  - Default: `/etc/prometheus`

* **alertmanager_path_config**: File system path
  - Default: `/etc/alertmanager`

* **prometheus_path_log**: Prometheus logs path
  - Default: `/var/log/prometheus`

* **prometheus_path_pid**: Prometheus PID path
  - Default: `/var/run/prometheus`

* **prometheus_path_data**: Prometheus Data path:
  - Default: `/var/lib/prometheus`

* **prometheus_path_rules**: Prometheus rules path:
  - Default: `{{ prometheus_path_config }}/rules`

* **prometheus_path_file_sd_config**: Prometheus file sd config path:
  - Default: `{{ prometheus_path_config }}/tgroups`

* **_prometheus_binary_install_dir**: Directory path
  - Default: `/usr/local/bin`

* **prometheus_components**: - alertmanager
  - Default: `[]`

* **prometheus_config_template**: Set the jinja2 template file to use instead of the provided one. Path based on playbook_dir

* **prometheus_version**: Prometheus version
  - Default: `1.7.1`

* **prometheus_service_name**: Prometheus service name
  - Default: `prometheus`

* **prometheus_listen_port**: Address to bind on, default :9090
  - Default: `9090`

* **prometheus_listen_address**: IP address
  - Default: `:{{ prometheus_listen_port }}`

* **prometheus_web_external_url**: If set, also set

* **prometheus_alertmanager_url**: URL of alert manager service

* **prometheus_scrape_interval**: Scrape interval: default 15s
  - Default: `15s`

* **prometheus_scrape_timeout**: Scrape timeout: default 10s
  - Default: `10s`

* **prometheus_evaluation_interval**: Evaluation interval: default 15s
  - Default: `15s`

* **alertmanager_version**: Alert manager version
  - Default: `0.8.0`

* **alertmanager_service_name**: Alert manager service name
  - Default: `alertmanager`

* **alertmanager_path_templates**: Alert manager template path
  - Default: `/etc/alertmanager/templates`

* **alertmanager_path_data**: Alert manager data path
  - Default: `/var/lib/alertmanager`

* **alertmanager_resolve_timeout**: ResolveTimeout is the time after which an alert is declared resolved if it has not been updated. default: 5m
  - Default: `5m`

* **alertmanager_smtp_from**: The default SMTP From header field. default empty

* **alertmanager_smtp_smarthost**: The default SMTP smarthost used for sending emails. default empty

* **alertmanager_smtp_auth_username**: SMTP authentication information. default empty

* **alertmanager_smtp_auth_password**: Password or authentication credential

* **alertmanager_smtp_auth_secret**: Secret credential or token

* **alertmanager_smtp_auth_identity**: Alert configuration

* **alertmanager_smtp_require_tls**: The default SMTP TLS requirement. default: false
  - Default: `False`

* **_alertmanager_binary_install_dir**: Directory path
  - Default: `/usr/local/bin`

* **alertmanager_slack_api_url**: Slack API url. default empty

* **nodeexporter_version**: Node exporter variables
  - Default: `0.14.0`

* **nodeexporter_service_name**: Node exporter service name
  - Default: `nodeexporter_{{ inventory_hostname_short }}`

* **nodeexporter_listen_port**: Node exporter listen address
  - Default: `9100`

* **nodeexporter_listen_address**: Network port number
  - Default: `:{{ nodeexporter_listen_port }}`

* **nodeexporter_collectors_enabled**: Collectors enables, comma-separated list of collectors to use. (default "conntrack,diskstats,entropy,edac,filefd,filesystem,hwmon,infiniband,loadavg,mdadm,meminfo,netdev,netstat,sockstat,stat,textfile,time,uname,vmstat,wifi,zfs")
  - Default: `conntrack,diskstats,entropy,edac,filefd,filesystem,hwmon,infiniband,loadavg,mdadm,meminfo,netdev,netstat,sockstat,stat,textfile,time,uname,vmstat,wifi,zfs`

* **_github_api_headers**: Variable used in: Discover latest version of prometheus
  - Default: `{{ {'GITHUB_TOKEN': lookup('ansible.builtin.env', 'GITHUB_TOKEN')} if (lookup('ansible.builtin.env', 'GITHUB_TOKEN')) else {} }}`

* **windowsexporter_version**: Node exporter variables
  - Default: `0.25.1`

* **windowsexporter_listen_port**: Node exporter listen address
  - Default: `9182`

* **eda_server_url**: URL or URI endpoint
  - Default: `aap.shadowman.dev`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: prometheus
      vars:
        prometheus_group: <value>
        prometheus_user: <value>
        prometheus_path_install: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
