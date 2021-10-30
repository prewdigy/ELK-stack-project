## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

TODO put image of network here


These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ELK-stack-project file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly redundant, in addition to restricting access to the network.  Load balancers also assist in security by protecting the site from DDoS attacks due to automatically balancing what ever the incoming traffic is between all the servers attached to it.   

The Jump Box allows for much more controlled access to the webservers 
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system services.  It does this using file beat and metric beat

The configuration details of each machine may be found below.

| Name            | Function  | IP Address | Operating System |
|-----------------|---------- |------------|------------------|
| Jump Box        | Gateway   | 10.0.0.4   | Linux            |
| Webserver-1     | Webserver | 10.0.0.5   | Linux            |
| Webserver-2     | Webserver | 10.0.0.6   | Linux            |
| ELK Stack       | Data logs | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 76.105.177.40

Machines within the network can only be accessed by the Jump Box machine.


A summary of the access policies in place can be found in the table below.

| Name         | Publicly Accessible | Allowed IP Addresses |
|--------------|---------------------|----------------------|
| Jump Box     | Yes                 | 76.105.177.40        |
| Webserver1:2 | No                  | 10.0.0.4             |
| Elk Stack    | Yes                 | 76.105.177.40        |

## Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it reduces the cost of labor, simplifies and speeds up the integration process when new machines/equipment are purchased, reduces human error, and increases disaster recory speed.

The playbook implements the following tasks:
-
- 
-   _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Webserver-1 10.0.0.5
- Webserver-2 10.0.0.6

We have installed the following Beats on these machines:
- File beat
- Metric beat

These Beats allow us to collect the following information from each machine:

- Filebeat is a lightweight shipper for forwarding and centralizing log data. Installed as an agent on your servers, Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.

- Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash. Metricbeat helps you monitor your servers by collecting metrics from the system and services running on the server.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the .yml file to /etc/ansible/roles.
- Update the hosts file to include the local IP addresses of the servers to be updated specified under [elk]
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running? http://[pubilc-IP-ELK server]:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
