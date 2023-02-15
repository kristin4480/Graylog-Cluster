# Graylog-Cluster
Automating the process of creating a highly available Graylog Cluster with Ansible


This project is for Linux servers only, that are running Ubuntu 20.04 LTS server as an OS

Software Requirements:
 * `ansible 2.12.9` or newer
 * `python version = 3.10.6` or newer
 * `jinja version = 3.0.3` or newer

In order for the playbook to work, you would need to add your custom information to the following files:
 * `inventory/hosts` - please add the addresses of your `graylog/mongo`, `elastic` and `haproxy` machine/s
 * `inventory/group_vars/graylog.yaml` -  please change the password for the admin panel for the Graylog UI
 * `inventory/group_vars/mongodb.yaml` -  please add information about the db `user` and db `password`, the rest of the configuration is entirely up to the end user
 * `haproxy.yaml` - please specify the absolute path to the `haproxy.cfg` file on your file system
 *  `inventory/group_vars/all.yaml` - add the sudo user and password for the remote machine/s


The command for running the ansible-playbook would be:


`ansible-playbook --become -i inventory/hosts main.yaml`


Of course this can be adjusted, as per the end user requirements
