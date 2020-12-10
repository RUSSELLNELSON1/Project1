## Automated ELK Stack Deployment
https://github.com/RUSSELLNELSON1/Project1/blob/main/Diagram/Diagram.jpg

The files in this repository were used to configure the network depicted below.

https://github.com/RUSSELLNELSON1/Project1

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ELK file may be used to install only certain pieces of it, such as Filebeat.

https://github.com/RUSSELLNELSON1/Project1/tree/main/Ansible

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
-Load balancing ensures that the application will be reliable; in addition to restricting access to the network.
-Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the files and system metrics.
-Filebeat collects data about file logs.
-Metricbeat collects machine metrics.

The configuration details of each machine may be found below.

| Name       | Function    | IP Address  | Operating System |
|--------------|---------------|----------------|-------------------------|
| Jump Box | Gateway    | 10.0.0.7      |            Linux            |
| web-1       |Web Server| 10.0.0.8      |            Linux            |
| Web-2      |Web Server| 10.0.0.9      |             Linux           |
| Web-3      |Web Server| 10.0.0.10    |            Linux            |
| ELK-1        |Elk Server    | 10.1.0.4      |            Linux            |

### Access Policies

-The machines on the internal network are not exposed to the public Internet. 
-Only the Jumpbox machine can accept connections from the Internet. 
-Access to this machine is only allowed from the admin Public ip address
-Machines within the network can only be accessed by Jumpbox.


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------------|---------------------|----------------------|
| Jump Box    | Yes/No              | 10.0.0.7              |
| Web Server| No                      | 10.0.0.1              |
| ELK Server  | No                      | 10.0.0.1              |
| Kibana         | Yes                     | Public IP             |
| DVWA         | Yes                     | Public IP              |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because its setup is within minutes using OpenSSH. There is also no need to install on the servers.  

The playbook implements the following tasks:
-Install Docker.io
-Increase Virtual Memory
-Download and Launch ELK Docker Container
-Make published ports available. 

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.
![ElkServer sudo_docker-ps caprture](https://user-images.githubusercontent.com/67285616/101830451-c1547880-3af1-11eb-825a-8c06aff6f428.png)


### Target Machines & Beats
This ELK server is configured to monitor the following machines:
•	Web-1 = ip: 10.0.0.8
•	Web-2 = ip: 10.0.0.9
•	Web-3 = ip: 10.0.0.10
We have installed the following Beats on these machines:
•	Metricbeat
•	Filebeat
These Beats allow us to collect the following information from each machine:
•	Filebeat monitors and forwards changed file logs. 
•	Metricbeat collects server metrics: Server up time, system logins, and data usage. 
### Using the Playbook
SSH into the control node and follow the steps below:
- Copy the Instal-Elk.yml file to /etc/ansible.
- Update the host file to include server admin iip’s and hosts.
- Run the playbook and navigate to the web servers to check that the installation worked as expected.
-Install -elk.yml and put in /etc/ansible folder
-Use file /etc/ansible/hosts to update the ip addresses to be installed with that playbook as well as which machine. 
-Navigate to http://10.1.0.4:5601 in order to check that the ELK server is running.


