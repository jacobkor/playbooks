### Using the Playbook

In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ansible playbook file to  /etc/ansible/files
- Update the install-elk.yml file to include ports, name, state, image, memory usage.
- Run the playbook, and navigate to http://[ELK-SERVER-PUBLIC-IP]:5061/ to check that the installation worked as expected.

### Using the Filebeat and Docker Metric Playbooks

***MAKE SURE YOUR ELK SERVER CONTAINER IS UP AND RUNNING

*** Filebeat Installation

- SSH into the control node and follow the steps below:
- Copy the ansible playbook and configuration files to  /etc/ansible/files
- Edit Filebeat-config.yml - scroll down to line #1106 and edit the hosts ip address to your ELK machine private ip address using port 9200, scroll down to line #1806 and edit the hosts ip address to your ELK machine prive ip address usinf port 5601. 
- save the file
- now run filebeat-playbook.yml to start the playbook and install filebeat 
***please note if the group you want to install file beat name is different then 'websrvers' please edit the file (filebeat-playbook.yml) and change line #3 hosts to the desire group name.

*** Dcoker metric Installation

still whitin ansible follow these steps below: 
- Copy the ansible playbook and configuration files to  /etc/ansible/files
- Edit metricbeat-config.yml - scroll down to line #62 and change the ip to your ELK machine private ip using port 5601, scroll down to line #96 and   change the hosts ip address to you ELK machine prive ip using port 9200.
- save the file 
- now run metricbeat.yml to start the playbook and install filebeat 
***please note if the group you want to install file beat name is different then 'websrvers' please edit the file (metricbeat.yml) and change line #3 host to the desire group name.

Answer the following questions to fill in the blanks:
-  Which file is the playbook? install-elk.yml  Where do you copy it? /etc/ansible/install-elk.yml
-  Which file do you update to make Ansible run the playbook on a specific machine? update the /etc/ansible/hosts file  How do I specify which machine   to install the ELK server on versus which to install Filebeat on? by specifying the group name (webservers/elk) - two groups we have set on the     hosts file. 
- Which URL do you navigate to in order to check that the ELK server is running? http://[ELK-SERVER-PUBLIC-IP]:5061/

commands to use:
 
 - All playbook and configurations files  can be downloaded using:   git clone https://github.com/jacobkor/playbooks.git
 - To update any of the .yml files use: nano <filname.yml> 
 - TO run a playbook use: ansible-playbook <file.yml>
