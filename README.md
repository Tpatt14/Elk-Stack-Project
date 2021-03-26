# Elk-Stack-Project
Elk stack and Diagrams 
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Images](/Images/Diagram_elkstack.png)

 

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - [YML_Playbooks](/YML_Playbooks/)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly Available, in addition to restricting inbound traffic to the network.

- a load balancer defends an organization against distributed (DDoS) attacks, it shifts attack traffic from the corporate server to a public cloud provider.
 
- A jump box is "hidden" to the public and can only be accessed by the administrator, it allows the adminitstrator to perform taks on the other machines.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- Filebeat monitors log files or lactions specified,collects logs events, and forwards them to Elasticsearch or Logstash for indexing. Logs can then be viewed in Kibana for easy interpretation. 

- Metricbeats records system metrics and statistics then sends them to the output chosen, the outputs are Elasticsearch or Logstash. These records can then be viewed in Kibana for easy interpretation.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name    | Function   | IP Address | Operating System     |
|---------|------------|------------|----------------------|
| Jump Box| Gateway    | 10.0.0.8   | Linux (Ubuntu 18.04) |
| Web-1   | Web Server | 10.0.0.5   | Linux (Ubuntu 18.04) |
| Web-2   | Web Server | 10.0.0.6   | Linux (Ubuntu 18.04) |
| Elk-P1  | Monitoring | 10.1.0.4   | Linux (Ubuntu 18.04) |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- The whitelisted IP addresses are, the administartors personal IP Address.

Machines within the network can only be accessed by other machines within the netowrk.
- The Jump Box was allowed to access the ELK VM, the IP address of the Jump Box is 10.0.0.8. 

A summary of the access policies in place can be found in the table below.

| Name    | Publicly Accessible  | Allowed IP Addresses      |
|---------|----------------------|---------------------------|
| Jumpbox | Yes                  | Administrators IP Address |
| Web-1   | No                   | 10.0.0.8                  |
| Web-2   | No                   | 10.0.0.8                  |
| Elk-P1  | No                   | 10.0.0.8                  |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
Automating configuration with Ansible is advantageous because it minimalizes mistakes, and finishes tasks in a timely mannner.  

The playbook implements the following tasks:
- Install Docker.io
- Install pyhton3-pip
- Install Docker module
- Increase virtual memory for machines on the network
- Download and launch a docker elk container
- Enable service Docker when the webservers are booted up  

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

[Images](/Images/Dokcer_ps.PNG.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web-1 10.0.0.5
- Web-2 10.0.0.6

We have installed the following Beats on these machines:
- I successfuly installed Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat: Detects changes to the filesystem, Filebeat is being used to monitor Web Log Data.

- Metricbeat: Detects changes in the systems metrics, such as system CPU. Metricbeats allows us to monitor uptime, CPU/Memory, and other data related services running on the servers. 

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
