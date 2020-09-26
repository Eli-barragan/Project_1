## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](https://github.com/Eli-barragan/Project_1/blob/master/Diagrams/Elk_diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Ansible file may be used to install only certain pieces of it, such as Filebeat.

  (https://github.com/Eli-barragan/Project_1/blob/master/Ansible/Install_elk.yml)

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly redundant, in addition to restricting accesss to the network.
- Load balancers make sure that servers and networks are available and accessable as much as possible.
- Having a jumpbox creates a single point of entry

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system logs.
- Filebeat monitors files and system logs
- Metricbeat monitors resource usages and prints it into human readable format

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1    |Webservers| 10.0.0.5   | Linux            |
| Web-2    |Webservers| 10.0.0.6   | Linux            |
| Web-3    |Webservers| 10.0.0.8   | Linux            |
| Elk_VM   |Webservers| 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 52.151.37.190

Machines within the network can only be accessed by Jump Box.
- The Elk_VM can only be accessed from the Jump Box through the ansible container using IP 10.1.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 52.151.37.190        |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Ansible allows for quick and consistant deployment of applications without having to configure each of your machines manually. You create playbooks that can launched whenever needed

The playbook implements the following tasks:
- Docker.io
- Install pip3
- Install Docker Python Module
- Increase virtual memory
- Use mem
- Downloaded and launched docker elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](https://github.com/Eli-barragan/Project_1/blob/master/Project_1/Images/Sudo%20docker%20ps%20in%20elk%20machine.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1 10.0.0.5
- Web-2 10.0.0.6
- Web-2 10.0.0.8

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat collects eventlogs on the webservers. These logs can be analyzed on Kibana to authenticate their integrity
- Metricbeat monitors resource usage on the machines, and sents it to Kibana to be analyzed

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the instal_elk.ylm file to /etc/ansible/files.
- Update the hosts file to include the private IP addresses of the machine you intend to run the playbook(s) on
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
(work in progress)
