# ansible-multiple-environements
# At first we need a clean and simple directory hierarchy 
# Execute 

ansible-playbook plays/<play-name> -i "<ENV>/hosts" -e @"environments/<ENV>/vars"

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
