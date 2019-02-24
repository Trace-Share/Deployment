
# Trace-Share: Deployment

Automated deployment of the Trace-Share framework to ease its installation within both testing and production environment.

[![Build Status](https://travis-ci.org/Trace-Share/Deployment.svg?branch=master)](https://travis-ci.org/Trace-Share/Deployment)

## Requirements

Trace-Share deployment is provided by [**Ansible**](https://www.ansible.com/) tool for automated installation and setting of all tools and systems required for the proper running of the Trace-Share framework. Ansible provisioning can be run on given server or on a local virtual machine powered by [**Vagrant**](https://www.vagrantup.com/) tool with [**VirtualBox**](https://www.virtualbox.org/) virtualization.

We are trying to stay up to date with the latest versions of all used software and provisioning tools. Be sure that you are using the latest versions Ansible, Vagrant, and VirtualBox to deploy the Trace-Share framework correctly.

## Local Deployment

Local deployment is primarily provided to ease testing and development of Trace-Share framework. It allows setting all used software and tools correctly without the requirement of deeper knowledge of individual Trace-Share framework parts. 

#### Ansible Configuration

Provision properties of the Trace-Share framework can be set in the [provisioning/core.yml](/provisioning/core.yml) file. See the documentation of individual roles in [provisioning/roles/](/provisioning/roles/) to see all available settings and their usage.

#### Virtual  Machine Configuration

All virtual machine properties can be set in Vagrantfile located in the root directory.  The default configuration uses the following settings that can be changed to fit the conditions of the guest machine:

```ruby
...
core.vm.network :private_network, ip:  "192.168.0.10", netmask:  "255.255.255.0"
core.vm.provider :virtualbox  do |v|
  v.customize ["modifyvm", :id, "--memory", 4096]
  v.customize ["modifyvm", :id, "--cpus", 2]
  ...
end
...
```

#### Basic Commands

Local deployment is provided by Vagrant tool, that can create a virtual machine and start Ansible provisioning automatically. Use the following commands to deploy and start the Trace-Share framework (for advanced usage see the Vagrant documentation):
- `$ vagrant up` – create and provision the virtual machine
- `$ vagrant up --no-provision` – create the virtual machine without provisioning
- `$ vagrant provision` – rerun provisioning script if an error occurred
- `$ vagrant destroy` – destroy the virtual machine

#### Usage

By default, the web interface of the Trace-Share framework is available on http://192.168.0.10 address that can be visited on the host machine. For login to the virtual machine use common Vagrant login credentials `vagrant:vagrant`.

## Remote Deployment

Deployment option is primarily intended for production setting of the Trace-Share framework on a publicly accessible server. It allows using all functionality of the framework without the need for any further knowledge.

#### Ansible Configuration

Provision properties of the Trace-Share framework can be set in the [provisioning/core.yml](/provisioning/core.yml) file. See the documentation of individual roles in [provisioning/roles/](/provisioning/roles/) to see all available settings and their usage. Role settings need to be set according to the environment of the server where the framework is deployed.

Remote deployment requires to specify the address and login credentials of the remote server in `provisioning/inventory.ini` file. Use [provisioning/inventory.ini.template](/provisioning/inventory.ini.template) as a template and specify the address of the server together with login credentials (username and SSH key).

### Basic Commands

Remote deployment is provided by Ansible provisioning that performs specified operations and set up the Trace-Share framework. Please note that the Ansible provisioning requires Python 3 installed on the remote server. Use the following command to start provisioning of the Trace-Share framework:

```console
$ ansible-playbook -i provisioning/inventory.ini provisioning/core.yml
```

## Contribution

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

*If you are interested in research collaborations, don't hesitate to contact us at  [https://csirt.muni.cz](https://csirt.muni.cz/about-us/contact?lang=en)!*
