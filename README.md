# Project-13
Unit 13 Project Kamden Popp
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

#(Images/rednetsetup.png)#

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - install-elk.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly accesable, in addition to restricting congestion to the network.


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system metrics.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  |52.250.11.56| Linux            |
| Redweb-1 | Webserver|  10.0.0.5  | Linux            |
| Redweb-2 | Webserver|  10.0.0.6  | Linux            |
| U13-VM   | ELK Stack|40.83.173.43| Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the U13-VM machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 71.218.235.71

Machines within the network can only be accessed by 71.218.235.71.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |         Yes         |    71.218.235.71     |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it 
allows all the settings to be readily visable and consistant.

The playbook implements the following tasks:
- Install docker any python with atp
- Install docker module with python (pip)
- Configuration for memory and port usage
- Confirm that docker is running

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

#(Images/docker.png)#

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
-10.0.0.5/6

We have installed the following Beats on these machines:
-Filebeat
-Metricbeat

These Beats allow us to collect the following information from each machine:
Filebeat collects information on files, all files, and metricbeat examines the metrics inside of said files. This allows us to see exactly whats going on within the server, or at least whats making its way through.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the install-elk.yml file to /etc/ansible.
- Update the hosts file to include ip address under ELK
- Run the playbook, and navigate to http://40.83.173.43:5601/app/kibana to check that the installation worked as expected.
