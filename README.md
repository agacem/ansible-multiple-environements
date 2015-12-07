# Ansible Multiple Environements

At first we need a clean and simple directory hierarchy 

# Hierarchy /etc/ansible/
			|- dev
				- hosts
				- vars
			|- int
				- hosts
				- vars
			|- prod
				- hosts
				- vars
			|- archives
			|- plays
				- play1.yml
				- play2.yml
				- ...
				- playN.yml
			|- roles
				|- mysqld
					|- files
					|- templates
					|- tasks
						- install.yml
						- main.yml
						- configure.yml
					|- handlers
						- main.yml
						- post-script1.yml
						- post-script2.yml
						- post-scriptN.yml
				|- httpd
					|- files
					|- templates
					|- tasks
					|- handlers
				|- haproxy
					|- files
					|- templates
					|- tasks
					|- handlers
				|- nginx
					...
				- ...
			- ReadMe
			- hosts
			- ansible.cfg
# Execute 

ansible-playbook plays/Playbook-name -i "ENV-Name/hosts" -e @"ENV-Name/vars"
