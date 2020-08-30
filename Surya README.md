## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![https://drive.google.com/file/d/1NMiK6sbGol4bb_2px0b-o4Pw7SlhsVvi/view?usp=sharing](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YML file may be used to install only certain pieces of it, such as Filebeat.

  - _ELK YML Text document which shows the script which was run 

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly availablity, in addition to restricting access to the network.
- Load Balancers protect availability of the information. A Jump box is a secure computer that all admins first connect to before launching any administrative task or sue as an origination point to connect to other servers or untrusted environments 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the servers and system logs.
- Filebeat monitors the log files or locations that you specify, collects log events and forwards them either to Elasticsearch or Logstash for indexing. 
- Takes the metrics and statics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash. Metricbeat helps you monitor your servers by collecting metrics from the system and services running on the server, such as: Apache.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web 1    | Server   | 10.0.0.5   | Linux            |
| Web 2    | Server   | 10.0.0.6   | Linux            |
| Web 3    | Server   | 10.0.0.7   | Linux            |
| ELK      | Server   | 10.1.0.5   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 20.185.71.215

Machines within the network can only be accessed by SSH.
- Web 2 40.87.27.194

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 20.185.71.215        |
| Web 1    | No                  | 10.0.0.5             |
| Web 2    | No                  | 10.0.0.6             |
| Web 3    | No                  | 10.0.0.7




### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Instead of manually keeping servers updated, making configurations, moving files, etc, we can use ansible to automate a group of servers from one control machine 

The playbook implements the following tasks:
- Install Docker 
- Install python3-pip 
- Increase virtual memory
- Download and lauch a docker elk container 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![Please see the attached image in GitHub titled Docker PS](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web 1 10.0.0.5
- Web 2 10.0.0.6


We have installed the following Beats on these machines:
- Web 2

These Beats allow us to collect the following information from each machine:
- File Beat is a lightweight shipper for forwarding and centralizing log data. Installed as an agent on your servers. Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing. 
- Metric Beat is a lightweight shipper that you can install on your servers to periodically collect metrics from the operating system and from services running on the server. Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify. 
- Packet Beat is a real-time network packet analyzer that can be used with Elasticsearch to provide an application monitoring and performance analytic system. Packetbeat sniffs the traffic between your servers, parses the application level protocols on the fly and correlates the messages into transactions

### Using the Playbook 
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the YML file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ELK server to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._