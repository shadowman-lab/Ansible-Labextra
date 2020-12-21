Creating and Launching Tower jobs
=========================

Ansible Tower allows you to get to single click automation job launches
or ask questions of the user at the time of automation to ensure
the end-user doesn't need to know automation.

Update Project
==================

In order to utilize the playbooks you've created, you'll first need
to update the Git project in Tower.

To do this, click Projects and then click the sync icon next to your project. 
Once this is complete, you can create the job template.

![Project Sync](images/1-project-sync.png)

Your Ansible Tower license has already been applied, so after
logging in you should now see the Dashboard.

Creating a Job Template
=============================

Now we have all of the pieces ready to create a Job Template and run our automation


Meraki Query
=============================

Step 1:
-------

Select **Templates**

Step 2:
-------

Click the ![Add](images/add.png) icon and select Job Template

Step 3:
-------

Complete the form using the following entries:

| Key         | Value                                                    | Note                             |
|-------------|----------------------------------------------------------|----------------------------------|
| Name        | Meraki Query                                             |                                  |
| Description | Template for Query of Meraki Devices                     |                                  |
| JOB TYPE    | Run                                                      |                                  |
| INVENTORY   | Localhost Inventory                                      | Update to be your Inventory name |
| PROJECT     | Ansible Workshop Project                                 | Update to be your project name   |
| PLAYBOOK    | `folder/query.yml`                                       | Add in your folder name          |
| CREDENTIAL  | Type: **Meraki Credential**. Name: **Meraki Credential** | Change to your cred name         |
| LIMIT       |                                                          |                                  |
| OPTIONS     |                                                          |                                  |

Step 4:
-------

Click SAVE ![Save](images/at_save.png)

Meraki SSID
=============================

Step 1:
-------

Select **Templates**

Step 2:
-------

Click the ![Add](images/add.png) icon and select Job Template

Step 3:
-------

Complete the form using the following entries:

| Key         | Value                                                    | Note                             |
|-------------|----------------------------------------------------------|----------------------------------|
| Name        | Meraki SSID Create                                       |                                  |
| Description | Template for SSID creation                               |                                  |
| JOB TYPE    | Run                                                      |                                  |
| INVENTORY   | Localhost Inventory                                      | Update to be your Inventory name |
| PROJECT     | Ansible Workshop Project                                 | Update to be your project name   |
| PLAYBOOK    | `folder/ssid.yml`                                        | Add in your folder name          |
| CREDENTIAL  | Type: **Meraki Credential**. Name: **Meraki Credential** | Change to your cred name         |
| LIMIT       |                                                          |                                  |
| OPTIONS     |                                                          |                                  |

Step 4:
-------

Click SAVE ![Save](images/at_save.png) and then select ADD SURVEY
![Add](images/at_add_survey.png)

Step 5:
-------

Complete the survey form with following values

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Enter Name for SSID                                                                                                                                    |                                              |
| DESCRIPTION             | SSID Name.                                                                                                                                              |                                              |
| ANSWER VARIABLE NAME    | ssid_name                                                                                                                                              |                                              |
| ANSWER TYPE             | Text                                                                                                                                                    |                                              |
| MINIMUM LENGTH          | 1                                                                                                                                                      |                                              |
| MAXIMUM LENGTH          | 1024                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button. You will
see your new field off to the right.

Step 6:
-------

Select SAVE ![Add](images/at_save.png)

Step 7:
-------

Back on the main Job Template page, select SAVE
![Add](images/at_save.png) again.

Meraki VLAN
=============================

Step 1:
-------

Select **Templates**

Step 2:
-------

Click the ![Add](images/add.png) icon and select Job Template

Step 3:
-------

Complete the form using the following entries:

| Key         | Value                                                    | Note                             |
|-------------|----------------------------------------------------------|----------------------------------|
| Name        | Meraki VLAN Create                                       |                                  |
| Description | Template for VLAN creation                               |                                  |
| JOB TYPE    | Run                                                      |                                  |
| INVENTORY   | Localhost Inventory                                      | Update to be your Inventory name |
| PROJECT     | Ansible Workshop Project                                 | Update to be your project name   |
| PLAYBOOK    | `folder/vlan.yml`                                        | Add in your folder name          |
| CREDENTIAL  | Type: **Meraki Credential**. Name: **Meraki Credential** | Change to your cred name         |
| LIMIT       |                                                          |                                  |
| OPTIONS     |                                                          |                                  |

Step 4:
-------

Click SAVE ![Save](images/at_save.png) and then select ADD SURVEY
![Add](images/at_add_survey.png)

Step 5:
-------

Complete the survey form with following values

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Enter a VLAN ID.                                                                                                                                        |                                              |
| DESCRIPTION             | VLAN ID.                                                                                                                                                |                                              |
| ANSWER VARIABLE NAME    | new_vlan_id                                                                                                                                            |                                              |
| ANSWER TYPE             | Integer                                                                                                                                                |                                              |
| MINIMUM                 | 0                                                                                                                                                      |                                              |
| MAXIMUM                 | 500                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button. You will
see your new field off to the right. Now add another field by filling out the form on the left again.

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Enter Subnet name                                                                                                                                      |                                              |
| DESCRIPTION             | Subnet Name                                                                                                                                            |                                              |
| ANSWER VARIABLE NAME    | subnet_name                                                                                                                                            |                                              |
| ANSWER TYPE             | Text                                                                                                                                                    |                                              |
| MINIMUM LENGTH          | 1                                                                                                                                                      |                                              |
| MAXIMUM LENGTH          | 1024                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button. You will
see two fields off to the right. Now add another field by filling out the form on the left again.

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Enter Subnet CIDR                                                                                                                                      |                                              |
| DESCRIPTION             | Subnet CIDR                                                                                                                                            |                                              |
| ANSWER VARIABLE NAME    | subnet_cidr                                                                                                                                            |                                              |
| ANSWER TYPE             | Text                                                                                                                                                    |                                              |
| MINIMUM LENGTH          | 1                                                                                                                                                      |                                              |
| MAXIMUM LENGTH          | 1024                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button. You will
see three fields off to the right. Now add another field by filling out the form on the left again.

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Enter Gateway IP                                                                                                                                        |                                              |
| DESCRIPTION             | Gateway IP                                                                                                                                              |                                              |
| ANSWER VARIABLE NAME    | gateway_ip                                                                                                                                              |                                              |
| ANSWER TYPE             | Text                                                                                                                                                    |                                              |
| MINIMUM LENGTH          | 1                                                                                                                                                      |                                              |
| MAXIMUM LENGTH          | 1024                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button.

Step 6:
-------

Select SAVE ![Add](images/at_save.png)

Step 7:
-------

Back on the main Job Template page, select SAVE
![Add](images/at_save.png) again.

Meraki Layer 3 Firewall Configuration
=============================

Step 1:
-------

Select **Templates**

Step 2:
-------

Click the ![Add](images/add.png) icon and select Job Template

Step 3:
-------

Complete the form using the following entries:

| Key         | Value                                                    | Note                             |
|-------------|----------------------------------------------------------|----------------------------------|
| Name        | Meraki Layer 3 Firewall Configuration                    |                                  |
| Description | Template for Layer 3 rule creation                       |                                  |
| JOB TYPE    | Run                                                      |                                  |
| INVENTORY   | Localhost Inventory                                      | Update to be your Inventory name |
| PROJECT     | Ansible Workshop Project                                 | Update to be your project name   |
| PLAYBOOK    | `folder/l3_firewall.yml`                                 | Add in your folder name          |
| CREDENTIAL  | Type: **Meraki Credential**. Name: **Meraki Credential** | Change to your cred name         |
| LIMIT       |                                                          |                                  |
| OPTIONS     |                                                          |                                  |

Step 4:
-------

Click SAVE ![Save](images/at_save.png) and then select ADD SURVEY
![Add](images/at_add_survey.png)

Step 5:
-------

Complete the survey form with following values

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Enter policy                                                                                                                                            |                                              |
| DESCRIPTION             | policy                                                                                                                                                  |                                              |
| ANSWER VARIABLE NAME    | policy                                                                                                                                                  |                                              |
| ANSWER TYPE             | Multiple Choice (single select)                                                                                                                        |                                              |
| MULTIPLE CHOICE OPTIONS | allow                                                                                                                                                  |                                              |
|                         | deny                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button. You will
see your new field off to the right. Now add another field by filling out the form on the left again.

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Select Protocol                                                                                                                                        |                                              |
| DESCRIPTION             | protocol                                                                                                                                                |                                              |
| ANSWER VARIABLE NAME    | protocol                                                                                                                                                |                                              |
| ANSWER TYPE             | Multiple Choice (single select)                                                                                                                        |                                              |
| MULTIPLE CHOICE OPTIONS | tcp                                                                                                                                                    |                                              |
|                         | udp                                                                                                                                                    |                                              |
|                         | icmp                                                                                                                                                    |                                              |
|                         | any                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button. You will
see two fields off to the right. Now add another field by filling out the form on the left again.

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Enter Source CIDR Separated by Commas                                                                                                                  |                                              |
| DESCRIPTION             | Source CIDR                                                                                                                                            |                                              |
| ANSWER VARIABLE NAME    | src_cidr                                                                                                                                                |                                              |
| ANSWER TYPE             | Text                                                                                                                                                    |                                              |
| MINIMUM LENGTH          | 1                                                                                                                                                      |                                              |
| MAXIMUM LENGTH          | 1024                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button. You will
see three fields off to the right. Now add another field by filling out the form on the left again.

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Enter Destination CIDRs Separated by Commas                                                                                                            |                                              |
| DESCRIPTION             | Destination CIDR                                                                                                                                        |                                              |
| ANSWER VARIABLE NAME    | dest_cidr                                                                                                                                              |                                              |
| ANSWER TYPE             | Text                                                                                                                                                    |                                              |
| MINIMUM LENGTH          | 1                                                                                                                                                      |                                              |
| MAXIMUM LENGTH          | 1024                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button. You will
see four fields off to the right. Now add another field by filling out the form on the left again.

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Enter Source Port (Or "any" to pick all ports                                                                                                          |                                              |
| DESCRIPTION             | Source Port                                                                                                                                            |                                              |
| ANSWER VARIABLE NAME    | src_port                                                                                                                                                |                                              |
| ANSWER TYPE             | Text                                                                                                                                                    |                                              |
| MINIMUM LENGTH          | 1                                                                                                                                                      |                                              |
| MAXIMUM LENGTH          | 1024                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button. You will
see five fields off to the right. Now add another field by filling out the form on the left again.

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Enter Desination Port (Or "any" to pick all ports                                                                                                      |                                              |
| DESCRIPTION             | Destination Port                                                                                                                                        |                                              |
| ANSWER VARIABLE NAME    | dest_port                                                                                                                                              |                                              |
| ANSWER TYPE             | Text                                                                                                                                                    |                                              |
| MINIMUM LENGTH          | 1                                                                                                                                                      |                                              |
| MAXIMUM LENGTH          | 1024                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button. You will
see six fields off to the right. Now add another field by filling out the form on the left again.

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Enter in a comment for the policy                                                                                                                      |                                              |
| DESCRIPTION             | Comment                                                                                                                                                |                                              |
| ANSWER VARIABLE NAME    | comment                                                                                                                                                |                                              |
| ANSWER TYPE             | Text                                                                                                                                                    |                                              |
| MINIMUM LENGTH          | 1                                                                                                                                                      |                                              |
| MAXIMUM LENGTH          | 1024                                                                                                                                                    |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |
Once complete, click the ADD ![Add](images/at_add.png) button.

Step 6:
-------

Select SAVE ![Add](images/at_save.png)

Step 7:
-------

Back on the main Job Template page, select SAVE
![Add](images/at_save.png) again.

Meraki Layer 7 Firewall Configuration
=============================

Step 1:
-------

Select **Templates**

Step 2:
-------

Click the ![Add](images/add.png) icon and select Job Template

Step 3:
-------

Complete the form using the following entries:

| Key         | Value                                                    | Note                             |
|-------------|----------------------------------------------------------|----------------------------------|
| Name        | Meraki Layer 7 Firewall Configuration                    |                                  |
| Description | Template for Layer 3 rule creation                       |                                  |
| JOB TYPE    | Run                                                      |                                  |
| INVENTORY   | Localhost Inventory                                      | Update to be your Inventory name |
| PROJECT     | Ansible Workshop Project                                 | Update to be your project name   |
| PLAYBOOK    | `folder/l7_firewall.yml`                                 | Add in your folder name          |
| CREDENTIAL  | Type: **Meraki Credential**. Name: **Meraki Credential** | Change to your cred name         |
| LIMIT       |                                                          |                                  |
| OPTIONS     |                                                          |                                  |

Step 4:
-------

Click SAVE ![Save](images/at_save.png) and then select ADD SURVEY
![Add](images/at_add_survey.png)

Step 5:
-------

Complete the survey form with following values

| Key                     | Value                                                                                                                                                  | Note                                         |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| PROMPT                  | Select Application                                                                                                                                      |                                              |
| DESCRIPTION             | Application                                                                                                                                            |                                              |
| ANSWER VARIABLE NAME    | app_name                                                                                                                                                |                                              |
| ANSWER TYPE             | Multple Choice (single select)                                                                                                                          |                                              |
| MULTIPLE CHOICE OPTIONS | Blogger                                                                                                                                                |                                              |
|                         | WordPress                                                                                                                                              |                                              |
|                         | Gmail                                                                                                                                                  |                                              |
|                         | Hotmail                                                                                                                                                |                                              |
| DEFAULT ANSWER          |                                                                                                                                                        |                                              |
| REQUIRED                | Selected                                                                                                                                                |                                              |

Once complete, click the ADD ![Add](images/at_add.png) button. You will
see your new field off to the right.

Step 6:
-------

Select SAVE ![Add](images/at_save.png)

Step 7:
-------

Back on the main Job Template page, select SAVE
![Add](images/at_save.png) again.

Running your New Playbooks
=============================

Now that you've created the playbooks, credentials, and job templates, you are ready to launch the automation jobs you've created.

Step 1:
-------

Select **Templates**

Step 2:
-------

Click the rocketship icon ![Add](images/at_launch_icon.png) for the Job Template you want to run
and answer any survey questions.

Step 3:
-------

Watch the playbook output and verify changes were made in Meraki!

<br><br>

[Click here to return to the Ansible for Meraki Workshop](https://github.com/shadowman-lab/Ansible-Meraki/tree/master/exercises)
