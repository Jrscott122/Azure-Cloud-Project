# Azure-Cloud-Project
Azure Cloud Project.
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO:](Images/AzureSystemDiagram.pdf)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the __yaml___ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO:

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly __available__, in addition to restricting __access___ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the __network___ and system __logs ___.
- _TODO: What does Filebeat watch for?_Filebeat watches log files and forwards alerts to the system
- _TODO: What does Metricbeat record?_metrics from OS, cpu memory and more

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| TODO     | Web-1    | 10.0.0.5   | Linux            |
| TODO     | Web-2    | 10.0.0.6   | Linux            |
| TODO     | Web-3    | 10.0.0.7   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the __Jumpbox___ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: public IP address _

Machines within the network can only be accessed by _SSHing from Jumpbox____.
- _TODO: 10.1.0.4_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible? Automating ansible allows for easy replication without human error.  Knowing the ansible yaml file will allow anyone to recreate the configuration the same way time and time again.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- The first step install docker uses the force_apt_get command to download software the second line (name) specifies docker.io as the software to download.
- The second step install pip uses force apt_get command to once again download software, this time python3-pip, this will allow us to download more python modules.
- The next step install docker pyton module uses pip to install the python module for docker.
- The 4th step increase virtual memory is a one step command used to increase the virtual memory of the system. the fifths step is a similar command but adds the virtual memory count to /etc/systcl.conf configuration file so the virtual machine will start with the same memory
- The final step is downloading and luanching of the elk container.  First it specifies the name, second the image name of the docker.  Then there are multiple settings, (state, restart_policy) Lastly the published ports.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/Capture.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: WEb-1 10.0.0.5 
         Web-2 10.0.0.6
         Web-3 10.0.0.7

We have installed the following Beats on these machines:
- _TODO: SystemLogs

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ___yaml__ file to __elk Server___.
- Update the ___configuration__ file to include.. proper webservers and proper hosts..
- Run the playbook, and navigate to __http://104.43.253.188:5601/app/kibana__ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_The playbook is the Yaml file? 
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? You update the configuration file.  The elk server is installed on what is listed under hosts, the Filebeats under webservers
- _Which URL do you navigate to in order to check that the ELK server is running? http://104.43.253.188:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
