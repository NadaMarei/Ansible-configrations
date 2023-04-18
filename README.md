# Ansible-labs-ITI

## Lab 1

### Ansible Playbook to Update Cash

This Ansible playbook is designed to update the cash of a web server by installing and configuring Nginx web server. The playbook includes tasks to update the package cache, install Nginx, copy an HTML file to the web server, and start the Nginx service.
Prerequisites

### Before running this playbook, you need to have the following:

    Ansible installed on your local machine
    SSH access to the target web server(s)
    The index.html file that you want to copy to the web server

### Playbook overview

#### The playbook consists of the following files:

    - ansible.cfg: The Ansible configuration file that sets up some default options for the playbook, such as the inventory file location, the private key to use for SSH authentication, and the remote user to use for SSH connections.
    - inventory: The Ansible inventory file that lists the target web server(s) to update. In this case, there is only one web server with the IP address 172.17.0.3.
    - update-cash-playbook.yaml: The Ansible playbook file that contains the tasks to update the cash. The tasks include updating the package cache, installing Nginx, copying the index.html file to the web server, and starting the Nginx service.
    index.html: The HTML file that will be copied to the web server.

### How to use the playbook

#### To use the playbook, follow these steps:

    1- Copy the index.html file to the same directory as the other playbook files (ansible.cfg, inventory, and update-cash-playbook.yaml).

    2- Edit the inventory file to list the IP addresses or hostnames of the web server(s) you want to update.

    3- Run the following command to execute the playbook:

    4- ansible-playbook update-cash-playbook.yaml -i inventory
    

    This will run the playbook and execute the tasks on the target web server(s).

#### After running the playbook, you should be able to access the index.html file in a web browser by entering the IP address of the web server(s) in the address bar.

### Conclusion

In this Ansible playbook, you learned how to use Ansible to update the cash of a web server by installing and configuring Nginx. You used Ansible tasks to update the package cache, install Nginx, copy an HTML file to the web server, and start the Nginx service. With this knowledge, you can expand the playbook to include other tasks for managing web servers, such as configuring SSL, setting up load balancing, or deploying web applications.




## Lab 2



