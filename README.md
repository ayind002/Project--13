# Project--13
Automated Elk Stack Development - Azure
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Project 13 Niyi. drawio.png](https://github.com/ayind002/Project--13/blob/main/Diagrams/Project%2013%20Niyi.%20drawio.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the yml file may be used to install only certain pieces of it, such as Filebeat.


This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting traffic to the network.

What aspect of security do load balancers protect?
Availability
Web Traffic
Web Security

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- _ What does Filebeat watch for?
Monitors the log files
locations that you specify
collects log events

- What does Metricbeat record?_
 Metrics and Statistics

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway   | 10.0.0.4  | Linux            |
| Elk      | ELK Server| 10.1.0.4  | Linux            |
| Web-1    | Web Server| 10.0.0.5  | Linux            |
| Web-2    | Web Server| 10.0.0.6  | Linux            |
| Web-3    | Web Server| 10.0.0.7  | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the Elk Server machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Azure Public IP Address TCP 5601

Machines within the network can only be accessed by JumpBox Provisioner through the workstation.
- Jump-Box-Provisioner IP: 10.0.0.4 though SSH port 22
  Workstation Pulic IP via port TCP 561

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses                 |
|----------|---------------------|----------------------                |
| Jump Box |      No              | Workstation Public IP through 22    |
| Web 1    |      No              | 10.0.0.5                            |
| Web 2    |      No              | 10.0.0.6                            |
| Web 3    |      No              |10.0.0.7                               |
| Elk Server|      No             |10.1.0.4                                   

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _The main advantage was the efficiently of running multiple programs within the container. Also very easy to use once installed and the ability to deploy multiples applications.

The playbook implements the following tasks:
- please see Ansible folder under the install-elk.yml file for further explanation of steps configuration.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![Please see Ansible folder under the install-elk.yml file for further explanation of steps configuration.t](https://github.com/ayind002/Project--13/blob/main/Ansible/Ansiblestuff.yml)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1 - 10.0.0.5
  Web-2 - 10.0.0.6

We have installed the following Beats on these machines:
- We installed FileBeat and Metricbeat.

These Beats allow us to collect the following information from each machine:
-In Filebeat the machine tracks log events that occurred, while the metric beat tracks the metrics and system analytics.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Ansible ELK Installation and VM Configuration.
- Run the playbook, and navigate to ansible-playbook install-elk.yml to check that the installation worked as expected.

Ran FileBeat Playing with the following command:
curl -L -O https://gist.githubusercontent.com/slape/58541585cc1886d2e26cd8be557ce04c/raw/0ce2c7e744c54513616966affb5e9d96f5e12f73/metricbeat > /etc/ansible/files/metricbeat-config.yml

 curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.6.1-amd64.deb
