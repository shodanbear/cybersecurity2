# cybersecurity2
The files in this repository were used to configure the network depicted below.

https://drive.google.com/file/d/114PxaYckVHltmQRTZmQe_xqJLTXFyHac/view?usp=sharing

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansibile playbook file may be used to install only certain pieces of it, such as Filebeat.

This document contains the following details:

Description of the Topologu
Access Policies
ELK Configuration
Beats in Use
Machines Being Monitored
How to Use the Ansible Build
Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network. -The off-loading function of a load balancer defends an organization against distributed denial-of-service

A jump server, jump host or jump box is a system on a network used to access and manage devices in a separate security zone. A jump server is a hardened and monitored device that spans two dissimilar security zones and provides a controlled means of access between them.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the system metrics and system logs.

The configuration details of each machine may be found below.

Name	Function	IP Address	Operating System
Jump Box	Gateway	10.0.0.4	Linux
Web01	VM	10.0.0.5	Linux
Web02	VM	10.0.0.7	Linux
Web03	VM	10.0.0.9	Linux
Access Policies
The machines on the internal network are not exposed to the public Internet.

Only the jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 71.199.35.212

Machines within the network can only be accessed by _____. See above

A summary of the access policies in place can be found in the table below.

Name	Publicly Accessible	Allowed IP Addresses
Jump Box	No	xxx.xxx.xxx.xxxx
Web01	No	10.0.0.4
web02	No	10.0.0.4
web03	No	10.0.0.4
Elk Configuration
Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it allows for easy automation across multiple machines within networks. The playbook implements the following tasks: Installing docker.io Installing python 3 pip Download and launch a docker web container Enable docker services

The following screenshots displays the result of running docker ps after successfully configuring the ELK instance.

https://drive.google.com/file/d/1HpgE434zk5tFC5bAy23D3xAovGLfT6Yc/view?usp=sharing https://drive.google.com/file/d/1QdkjEZzxTU8kUGnVqRr3lCvqrRC4e_ys/view?usp=sharing

Target Machines & Beats
This ELK server is configured to monitor the following machines: 10.0.0.5 10.0.0.7 10.0.0.9

We have installed the following Beats on these machines: Filebeat Metricbeat

These Beats allow us to collect the following information from each machine: Filebeats is a lightweight shipper for forwarding and centralizing log data. Installed as an agent on your servers, Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.

Metric beats takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash. Metricbeat helps you monitor your servers by collecting metrics from the system and services running on the server

Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below: In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:

Copy the beat configuration file file to files directory.
Update the hosts file to include the additional ip address
Run the playbook, and navigate to http://40.65.224.227:5601/app/kibana#/home?_g=() to check that the installation worked as expected.
