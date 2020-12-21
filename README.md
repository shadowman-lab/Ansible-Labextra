# Ansible-Labextra
Extra playbooks for connecting with outside resources/lab setup

Demos for SE Management SSP for use with customers to showcase different aspects of Ansible

# Roles
Current roles in requirements.yml is for prometheus and grafana

# Templates

elasticsearch.yml.j2
>Elasticsearch configuration file for use with ELKBuild.yml

logstash.conf
>Logstash configuration file for use with ELKBuild.yml

prometheus.yml.j2
>sets up prometheus config for use with grafana

# Playbooks

ELKBuild.yml
>Build full ELK stack including Kibana. Kibana web address will be viewable at the IP address:5601

Email.yml
>Send email to variable {{ to_email }}. E-mail host information stored in Ansible Tower credentials. Depends on set_facts for {{ email_ip_address }} in order to e-mail weblink for created web site

eventautoprep.yml
>prepares prometheus for a demo to scape data more or less often

Nodeexporter.yml
>Install Prometheus Node Exporter and setup firewalld

Promgraf.yml
> Install prometheus and grafana and setup firewalld
