# Lab 1 : Ansible Playbook to Update Cash

This Ansible playbook is designed to update the cash of a web server by installing and configuring Nginx web server. The playbook includes tasks to update the package cache, install Nginx, copy an HTML file to the web server, and start the Nginx service.
Prerequisites

### Before running this playbook, you need to have the following:

    - Ansible installed on your local machine
    - SSH access to the target web server(s)
    - The index.html file that you want to copy to the web server

### Playbook overview

#### The playbook consists of the following files:

    - ansible.cfg: The Ansible configuration file that sets up some default options for the playbook, such as the inventory file location, the private key to use for SSH authentication, and the remote user to use for SSH connections.
    
    - inventory: The Ansible inventory file that lists the target web server(s) to update. In this case, there is only one web server with the IP address 172.17.0.3.
    
    - update-cash-playbook.yaml: The Ansible playbook file that contains the tasks to update the cash. The tasks include updating the package cache, installing Nginx, copying the index.html file to the web server, and starting the Nginx service.
    
    - index.html: The HTML file that will be copied to the web server.

### How to use the playbook

#### To use the playbook, follow these steps:

    1- Copy the index.html file to the same directory as the other playbook files (ansible.cfg, inventory, and update-cash-playbook.yaml).

    2- Edit the inventory file to list the IP addresses or hostnames of the web server(s) you want to update.

    3- Run the following command to execute the playbook:

        ansible-playbook update-cash-playbook.yaml -i inventory
    

    This will run the playbook and execute the tasks on the target web server(s).

#### After running the playbook, you should be able to access the index.html file in a web browser by entering the IP address of the web server(s) in the address bar.

### Conclusion

In this Ansible playbook, you learned how to use Ansible to update the cash of a web server by installing and configuring Nginx. You used Ansible tasks to update the package cache, install Nginx, copy an HTML file to the web server, and start the Nginx service. With this knowledge, you can expand the playbook to include other tasks for managing web servers, such as configuring SSL, setting up load balancing, or deploying web applications. </br>




# Lab 2 : Ansible Playbooks for Web Server Configuration

This repository contains multiple Ansible playbooks that can be used to configure a web server. Each playbook focuses on a specific task, such as installing and configuring Nginx or managing packages using loops and variables.
Prerequisites

### Before running these playbooks, you need to have the following:

    - Ansible installed on your local machine
    - SSH access to the target web server(s)

### Playbook overview

#### This repository contains the following files:

    - ansible.cfg: The Ansible configuration file that sets up some default options for the playbooks, such as the inventory file location, the private key to use for SSH authentication, and the remote user to use for SSH connections.
    
    - inventory: The Ansible inventory file that lists the target web server(s) to configure. In this case, there are two web servers with the IP addresses 172.17.0.3 and 172.17.0.4.
    
    - nginx-httpd.yaml: The Ansible playbook file that installs and configures Nginx and Apache HTTP server on the target web server(s). The playbook includes tasks to install Nginx and Apache HTTP server, and restart the services if necessary.
    
    - nginx-tags.yaml: The Ansible playbook file that demonstrates the use of tags in Ansible. The playbook includes tasks to update the package cache, install Nginx, and display Ansible facts. Each task is associated with a tag that can be used to selectively execute tasks.
    
    - nginx-vars.yaml: The Ansible playbook file that demonstrates the use of variables in Ansible. The playbook includes tasks to update the package cache and install Nginx, using variables for the package name and state.
    
    - package-loops.yaml: The Ansible playbook file that demonstrates the use of loops in Ansible. The playbook includes tasks to update the package cache, install and configure multiple packages using a loop, and convert the package state using another loop.
    
    - vars.yaml: The Ansible variable file that defines the variables used in the nginx-vars.yaml and package-loops.yaml playbooks.
    

### How to use the playbooks

#### To use the playbooks, follow these steps:

    1- Edit the inventory file to list the IP addresses or hostnames of the web server(s) you want to configure.

    2- Run the following command to execute a playbook:

        ansible-playbook playbook-file.yaml -i inventory

    3- Replace `playbook-file.yaml` with the name of the playbook you want to execute.
    

#### After running the playbook(s), the web server(s) should be configured according to the tasks in the playbook(s).

### Conclusion

In these Ansible playbooks, you learned how to use Ansible to configure a web server by installing and configuring Nginx and Apache HTTP server, managing packages using tags, variables, and loops. With this knowledge, you can create more complex playbooks to manage web servers, such as configuring SSL, setting up load balancing, or deploying web applications.


# Lab 3 : Ansible Role for Web Server Configuration

This Ansible role installs and configures a web server by installing Nginx, updating the package cache, and copying HTML and CSS files to the web server. The role includes a tasks folder that defines the tasks to be performed, a templates folder that contains the HTML template file, a files folder that contains the CSS file, a handlers folder that defines the handlers to be executed, and a vars folder that defines the variables used in the role.
Prerequisites

### Before running this role, you need to have the following:

    - Ansible installed on your local machine
    - SSH access to the target web server(s)

### Role overview

This role consists of the following files and folders:

    - ansible.cfg: The Ansible configuration file that sets up some default options for the role, such as the inventory file location, the private key to use for SSH authentication, and the remote user to use for SSH connections.
    
    - inventory: The Ansible inventory file that lists the target web server(s) to configure. In this case, there are two web servers with the IP addresses 172.17.0.3 and 172.17.0.4.
    
    - web.yaml: The Ansible playbook file that applies the web role to the target web server(s).
    
    - web folder: The Ansible role folder that contains the tasks, templates, files, handlers, and variables for the role.

#### Tasks

##### The tasks folder contains the main tasks for the role. These tasks include:

    - Updating the package cache using the apt module.
    - Installing Nginx using the package module and notifying the restart-nginx handler.
    - Removing Nginx using the package module and notifying the restart-nginx handler.
    - Notifying the restart-nginx handler when Nginx is installed or removed.

#### Templates

The templates folder contains the `HTML` template file that will be copied to the `web server`. The template includes a `placeholder` for the name of the user, which will be replaced with the actual name during the `playbook` execution.

#### Files

The files folder contains the `CSS` file that will be copied to the `web server`. The CSS file defines the style for the HTML template.

#### Handlers

##### The handlers folder contains the handlers that will be triggered by the tasks. These handlers include:

    - Restarting Nginx using the sysvinit module.
    - Copying the HTML template to the web server using the template module and notifying the copy_style handler.
    - Copying the CSS file to the web server using the copy module.

#### Variables

##### The vars folder contains the variables used in the role. These variables include:

    - The package name and state for Nginx.
    - The name to be displayed in the HTML template.

### How to use the role

#### To use the role, follow these steps:

    1- Edit the inventory file to list the IP addresses or hostnames of the web server(s) you want to configure.

    2- Edit the web.yaml playbook file to include the web role.

    3- Run the following command to execute the playbook:

        ansible-playbook web.yaml -i inventory
    

#### After running the playbook, the web server(s) should be configured according to the tasks in the role.

### Conclusion

With this Ansible role, you learned how to use Ansible to configure a web server by installing Nginx, updating the package cache, and copying HTML and CSS files to the web server. This role can be extended to include additional tasks, such as configuring SSL or deploying web applications.
