# -*- mode: ruby -*-
# vi: set ft=ruby :

# """
# Provisioning may take a long time, do not stop it or suspend it earlier, it
# can cause unexpected behavior.
#
#
# Usage:
#  * vagrant up              -- deploy and provision
#  * vagrant up <node name>  -- deploy and provision specified node
#  * vagrant halt            -- stop the running guest
#  * vagrant destroy         -- destroy the deployed guest
#  * vagrant -h              -- show common vagrant commands
# """


# """
# All Vagrant configuration is done below.
#
# The "2" in Vagrant.configure configures the configuration version (Vagrant
# support older styles for backward compatibility). Please don't change it
# unless you know what you're doing.
# """
Vagrant.configure("2") do |config|
  # For a complete reference of configuration, please see the online documentation at https://docs.vagrantup.com

  config.vm.define "core.trace-share" do |core|
    core.vm.hostname = "core.trace-share"
    core.vm.box = "ubuntu/bionic64"
    core.vm.network :private_network, ip: "192.168.0.10", netmask: "255.255.255.0"
    core.vm.synced_folder "./", "/vagrant"
    core.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--name", "core.trace-share"]
      v.customize ["modifyvm", :id, "--memory", 4096]
      v.customize ["modifyvm", :id, "--cpus", 2]
      v.customize ["modifyvm", :id, "--uartmode1", "disconnected"]
    end
    
    core.vm.provision :ansible_local do |ansible|
      ansible.install_mode = "pip"  # Use the latest Ansible
      ansible.become = true
      ansible.playbook = "/vagrant/provisioning/core.yml"
    end
  end
end
