Writing a Playbook
=========================

There are a number of editors you can use to write playbooks, VS Code
is typically the easiest to use, but any editor works. Log in to your
favorite editor

Writing the playbooks
==================

You will be creating 5 different playbooks to interact with the Meraki API.
We will then pull them into Ansible Tower and leverage surveys for the variables
you create.
Inside the repository, create an additional folder with your last name to keep track
of your specific playbooks. All the playbooks you make will live inside that folder.

Playbook 1:
-------
Create a file called `query.yml` in your folder. Enter the following code:
```
---

- name: Meraki Query
  hosts: localhost
  gather_facts: false
  
  tasks:
    - name: List all networks associated to the {{ org_name }} organization
      meraki_network:
        state: query
        org_name: "{{ org_name }}"
      register: network
      
    - name: Show lists
      debug:
        var: network
```
Reminder, org_name is a variable that we will create later in Ansible Tower

Playbook 2:
-------
Create a file called `ssid.yml` in your folder. Enter the following code:
```
---

- name: Meraki SSID Playbook
  hosts: localhost
  gather_facts: false
    
  tasks:
    - name: Create an SSID.
      meraki_ssid:
        org_name: "{{ org_name }}"
        net_name: "{{ net_name }}"
        state: present
        name: "{{ ssid_name }}"
        enabled: true
      delegate_to: localhost
```

Reminder, org_name and net_name are variables that we will create later in Ansible Tower.
ssid_name will be a variable we answer with a survey in Tower

Playbook 3:
-------
Create a file called `vlan.yml` in your folder. Enter the following code:
```
---

- name: Meraki Playbook to create a VLAN
  hosts: localhost
  gather_facts: false
    
  tasks:
      
    - name: Create a VLAN.
      meraki_vlan:
        org_name: "{{ org_name }}"
        net_name: "{{ net_name }}"
        state: present
        vlan_id: "{{ new_vlan_id }}"
        name: "{{ subnet_name }}"
        subnet: "{{ subnet_cidr }}"
        appliance_ip: "{{ gateway_ip }}"
      delegate_to: localhost
```
Reminder, org_name and net_name are variables that we will create later in Ansible Tower.
The rest will be answered in a Survey in Ansible Tower

Playbook 4:
-------
Create a file called `l3_firewall` in your folder. Enter the following code:
```
---

- name: Meraki Layer 3 Firwaall Configuration
  hosts: localhost
  gather_facts: false

  tasks:
    - name: Set a Layer 3 firewall rule
      meraki_mx_l3_firewall:
        org_name: "{{ org_name }}"
        net_name: "{{ net_name }}"
        state: present
        rules:
          - comment: "{{ comment }}"
            src_cidr: "{{ src_cidr }}" 
            src_port: "{{ src_port }}"
            dest_cidr: "{{ dest_cidr }}"
            dest_port: "{{ dest_port }}"
            protocol: "{{ protocol }}"
            policy: "{{ policy }}"
      delegate_to: localhost
```
All of the rules will be answered via a Survey in Ansible Tower

Playbook 5:
-------
Create a file called `l7_firewall.yml` in your folder. Enter the following code:
```
---

- name: Meraki Layer 7 Firewall Configuration
  hosts: localhost
  gather_facts: false

  tasks:
    - name: Set some example Layer 7 firewall rules
      meraki_mx_l7_firewall:
        org_name: "{{ org_name }}"
        net_name: "{{ net_name }}"
        state: present
        rules:
          - policy: deny
            type: application
            application:
              name: "{{ app_name }}"
      delegate_to: localhost
```
This module will overwrite any existing l7 rules. A Tower survey will provide
the app_name.

Commit to Git
==================
Commit all of your changes to your respository. Login to the respository to verify
that your folder exists with the 5 playbooks inside.

<br><br>

[Click here to return to the Ansible for Meraki Workshop](https://github.com/shadowman-lab/Ansible-Meraki/tree/master/exercises)
