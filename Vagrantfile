# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Vagrant virtual machines require a box to build off of.
  config.vm.box = "voidlinux/glibc64"
  # disable updating guest additions
  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.auto_update = false
  end
  # disable guest additions
  config.vm.synced_folder '.', '/vagrant', disabled: true

  config.vm.define 'vagrant1' do |vagrant1|
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    vagrant1.vm.network "private_network", ip: "192.168.56.10"
    vagrant1.vm.hostname = "vagrant1"
    vagrant1.vm.provider "virtualbox" do |vb|
      vb.name = "vagrant1"
      # Use VBoxManage to customize the VM. For example to change memory:
      vb.customize ["modifyvm", :id, "--memory", "5024"]
    end
  end

  config.vm.define 'vagrant2' do |vagrant2|
    # Create a private network, which allows host-only access to the machine
    # using a specific IP.
    vagrant2.vm.network "private_network", ip: "192.168.56.11"
    vagrant2.vm.hostname = "vagrant2"
    vagrant2.vm.provider "virtualbox" do |vb|
      vb.name = "vagrant2"
      # Use VBoxManage to customize the VM. For example to change memory:
      vb.customize ["modifyvm", :id, "--memory", "5024"]
    end
  end

end
