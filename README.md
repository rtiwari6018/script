## Automated ELK Stack Deployment
 
The files in this repository were used to configure the network depicted below.
 

![TODO: Update the path with the name of your diagram](diagrams/HomeWKDiagram.PNG)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Ansible file may be used to install only certain pieces of it, such as Filebeat.

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

Load balancing ensures that the application will be highly <u>Responsive</u>, in addition to restricting <u> Traffic</u> to the network.

- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
ANS:-Load Balancing plays an important security role as computing moves 
evermore to the cloud. The off-loading function of a load balancer 
defends an organization against distributed denial-of-service (DDoS) attacks.

A jump box is a secure computer that all admins first connect to 
before launching any administrative task or use as an origination 
point to connect to other servers or untrusted environments.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the <U>LOGS</U> and system <U>Matrics</u>.
- _TODO: What does Filebeat watch for?

Ans:----That has been changed, and when the change took place.

- _TODO: What does Metricbeat record?

Ans:-Metricbeat is a lightweight shipper that you can install
on your servers to periodically collect metrics from the
operating system and from services running on the server.
Metricbeat takes the metrics and statistics that it collects
and ships them to the output that you specify, such as 
Elasticsearch or Logstash.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name       | Function            | IP Address | Operating System |
|------------|---------------------|------------|------------------|
| Jumpbox    | Gateway             | 10.0.0.4   | Linux            |
| Web-1      | Webserver           | 10.0.0.5   | Linux            |
| Web-2      | Webserver           | 10.0.0.6   | Linux            |
| Web-3      | Webserver           | 10.0.0.7   | Linux            |
| ELK server | LogMonitoringServer | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the <u>JumpBox</u> machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:Public IP 137.117.19.233

- _TODO: Add whitelisted IP addresses_HomePublic IPaddress.

Machines within the network can only be accessed by <u> Jumpbox_</u>.

- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_Through Home machine and Home PUBLIC address.

A summary of the access policies in place can be found in the table below.

| Name    	| Publicly Accessible 	| Allowed IP address           	|
|---------	|---------------------	|------------------------------	|
| JumpBox 	| No                  	| 10.0.0.4 and Home IP address 	|
| Web-1   	| NO                  	| 10.0.0.5                     	|
| Web-2   	| No                  	| 10.0.0.6                     	|
| ElkVM   	| No                  	| Home IP Address              	|

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

Ans -This allows you to deploy to multiple servers using a single playbook.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Ans:=
The playbook implements the following tasks:

Install docker.io
Install Python-pip
Install docker container
Launch docker container: elk
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

**Note**: The following image link needs to be updated. Replace `docker_ps_output.png` with the name of your screenshot image file.  


![TODO: Update the path with the name of your screenshot of docker ps output](Images/Docker_PS_Output.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
Ans:-Web-1 10.0.0.5
     Web-2 10.0.0.6
     Web-3 10.0.0.7


We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_Beats

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

Ans:-Beats are essentially lightweight, purpose-built agents 
that acquire data and then ,customized beats for any 
type of data you'd like to send to Elasticsearch. While
 each beat has its own distinct use, they all solve the common
 problem . As the name implies,  Winlogbeat can capture event data from any event logs running on your system. from servers and systems.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the <u>install-elk.yml </u>file to <u>the ansible container</u>
- Update the <u>host</u> file to include...
- Run the playbook, and navigate to <u> ipaddress:5601/app/kibana</u> to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
curl https://raw.githubusercontent.com/rtiwari6018/script/main/ansible/install-elk.yml > /etc/ansible/install.elk.yml
