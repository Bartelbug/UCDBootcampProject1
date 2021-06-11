## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![ELK Stack Network Diagram](https://github.com/Bartelbug/UCDBootcampProject1/blob/main/HWwk12.jpg)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yml file may be used to install only certain pieces of it, such as Filebeat.

  - _https://github.com/Bartelbug/UCDBootcampProject1/commit/3cbce9684df08b3672f730266de70a5a934cd8f0._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly avalible, in addition to restricting access to the network.
- Load balancers protect the network by only exposing one IP address to the public internet, the jump box also protects in this way by forcing all administration to flo through the jump box.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the web servers and system logs.
-Filebeat monitors the system logs for search with Elastic
-Metricbeat monitors system statistics

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name         | Function  | Internal IP | Public IP      | OS           |
|--------------|-----------|-------------|----------------|--------------|
| Bug-VM1      | Jumpbox   | 10.0.0.10   | 52.183.99.223  | Ubuntu 18.04 |
| Bugweb1v2-VM | Webserver | 10.0.0.21   | 51.141.188.172 | Ubuntu 20.04 |
| Bugweb2v2-VM | Webserver | 10.0.0.22   | 51.141.188.172 | Ubuntu 20.04 |
| ELK-VM2      | ELK Stack | 10.0.0.31   | 40.124.29.79   | Ubuntu 20.04 |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
98.242.33.53
Machines within the network can only be accessed by the Jumpbox.
The ELK Stack is accessible from 98.242.33.53

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
