## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![ELK Stack Network Diagram](https://github.com/Bartelbug/UCDBootcampProject1/blob/main/HWwk12.jpg)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yml file may be used to install only certain pieces of it, such as Filebeat.

  https://github.com/Bartelbug/UCDBootcampProject1/commit/3cbce9684df08b3672f730266de70a5a934cd8f0

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

| Name      | Port | Publicly Accessible | Allowed IP Addresses |
|-----------|------|---------------------|----------------------|
| Jumpbox   | 22   | Yes                 | 98.242.33.53         |
| Webserver | 80   | Yes                 | 98.242.33.53         |
| ELK Stack | 5601 | Yes                 | 98.242.33.53         |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
-Ansible allows the rapid deployment of multiple containers in a short period of time.

The playbook implements the following tasks:
- Installs Docker
- Installs ELK omn Elk server
- Installs Filebeat and copies config file to webservers
- Installs Metricbeat and copies config file to webservers

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

!(https://github.com/Bartelbug/UCDBootcampProject1/blob/main/Screenshot%202021-05-27%20211114.jpg)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-10.0.0.21
-10.0.0.22

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat will monitor the systemlogs of the web servers, allowing us to see any login attempts or system configuration changes. Metricbeat will monitor system performance and load, allowing visibility on items like cpu load, network performance and storage usage.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ELKwithWEB.yml, filebeat-config.yml, and metricbeat-config.yml to /etc/ansible.
- Update the hosts file to include the elk group with ip of the elk server and the webservers group with the ip addresses of the webservers 
- Run the playbook, and navigate to 40.124.29.79:5601 to check that the installation worked as expected.

