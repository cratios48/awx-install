# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.hostname = "awx-test"
  config.vm.network "private_network", ip: "10.10.10.10"
  config.vm.provider "virtualbox" do |v|
    v.cpus = 2
    v.memory = 4096
  end

  config.vm.provision "ansible_local" do |a|
    a.install           = true
    a.version           = 'latest'
    a.install_mode      = 'pip'
    a.inventory_path    = 'inventory.yaml'
    a.limit             = 'all'
    a.playbook          = 'awx.yaml'
  end
end