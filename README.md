<!-- This was created with Claude Code -->

# Labextra Automation

[![Contribute](https://img.shields.io/badge/OpenShift-Dev%20Spaces-525C86?logo=redhatopenshift&labelColor=EE0000)](https://devspaces.apps.ocp.shadowman.dev/#https://github.com/shadowman-lab/Ansible-Labextra)


This directory contains Ansible automation for labextra management and operations.

## Overview

The Labextra automation provides playbooks and roles for managing and configuring
labextra infrastructure and services.

## Roles

| Role | Description |
| ---- | ----------- |
| [auditbeat](roles/auditbeat/README.md) | Role for auditbeat |
| [datadog_remove](roles/datadog_remove/README.md) | Role for datadog remove |
| [elk_build](roles/elk_build/README.md) | Role for elk build |
| [email](roles/email/README.md) | Role for email |
| [grafana_deploy](roles/grafana_deploy/README.md) | Role for grafana deploy |
| [jenkins_setup](roles/jenkins_setup/README.md) | Role for jenkins setup |
| [kafka](roles/kafka/README.md) | Role for kafka |
| [prometheus](roles/prometheus/README.md) | Role for prometheus |
| [shadowman_telegraf](roles/shadowman_telegraf/README.md) | Role for shadowman telegraf |
| [snort_build](roles/snort_build/README.md) | Role for snort build |
| [snort_config](roles/snort_config/README.md) | Role for snort config |
| [winlogbeat](roles/winlogbeat/README.md) | Role for winlogbeat |

## Playbooks

| Playbook | Description | Target Hosts |
| -------- | ----------- | ------------ |
| ELKBuild.yml | Playbook for ELKBuild | all |
| Elastic_restart.yml | Playbook for Elastic restart | all |
| Nodeexporter.yml | Playbook for Nodeexporter | all |
| Promgraf.yml | Playbook for Promgraf | all |
| auditbeatinstall.yml | Playbook for auditbeatinstall | all |
| datadogagentinstall.yml | Playbook for datadogagentinstall | {{ vm_name | default('all') }} |
| datadogagentremove.yml | Playbook for datadogagentremove | {{ vm_name | default('all') }} |
| dynatraceagent.yml | Playbook for dynatraceagent | all |
| email.yml | Playbook for email | all |
| eventautoprep.yml | Playbook for eventautoprep | all |
| jenkins.yml | Playbook for jenkins | localhost |
| kafkainstall.yml | Playbook for kafkainstall | all |
| snortbuildconfig.yml | Playbook for snortbuildconfig | all |
| telegraf.yml | Playbook for telegraf | kafka.shadowman.dev |
| windowsexporter.yml | Playbook for windowsexporter | all |
| winlogbeatinstall.yml | Playbook for winlogbeatinstall | all |

## Usage

### Running with ansible-navigator

```bash
# Run a playbook
ansible-navigator run ELKBuild.yml

# Run in stdout mode
ansible-navigator run ELKBuild.yml -m stdout
```

### Using roles

```yaml
- hosts: target_hosts
  roles:
    - auditbeat
```

## Requirements

- Ansible 2.9 or higher (via ansible-navigator)
- Required collections (see `collections/requirements.yml` if present)
- Appropriate access credentials configured via environment variables

## Directory Structure

```
Ansible-Labextra/
├── roles/              # Ansible roles
├── *.yml               # Playbooks
├── collections/        # Collection dependencies (if present)
└── ansible-navigator.yml  # Navigator configuration
```
