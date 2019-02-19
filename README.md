# Deployment

Automated deployment of the Trace-Share environment

[![Build Status](https://travis-ci.org/Trace-Share/Deployment.svg?branch=master)](https://travis-ci.org/Trace-Share/Deployment)

## Basic Commands

The deployment is provided by [Vagrant](https://www.vagrantup.com/) and [Ansible](https://www.ansible.com/) tools. To control deployment with virtual machine in the [VritualBox](https://www.virtualbox.org/) use the following commands:
- `$ vagrant up` – create and provision the server virtual machine
- `$ vagrant up --no-provision` – create the server virtual machine without provisioning
- `$ vagrant provision` – rerun provisioning script if an error occurred
- `$ vagrant destroy` – destroy the server virtual machine
