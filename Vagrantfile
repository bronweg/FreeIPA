# -*- mode: ruby -*-
# vi: set ft=ruby :
VM_CPU = "2"
VM_MEMORY = "2048"
VM_NAME = "test.my.domain"
VM_IP = "192.168.205.129" #Don't worry, if you don't have such sub-network - it will be created.

Vagrant.configure("2") do |config|
  config.vagrant.plugins = "vagrant-vbguest"
  config.vbguest.auto_update = false
  config.vbguest.yes = true
  config.vm.box = "centos/7"
  config.vm.network "private_network", ip: VM_IP
  config.vm.hostname = "test.my.domain"

  config.vm.define VM_NAME

  config.vm.provider "virtualbox" do |v|
    v.name = VM_NAME
  end

  config.vm.provider "virtualbox" do |v|
    v.cpus = VM_CPU
    v.memory = VM_MEMORY
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
    ansible.inventory_path = "provisioning/hosts"
    ansible.ask_vault_pass = false
  end
end
