# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.define "slave1" do |m|
    m.vm.box = "ubuntu/trusty64"
    m.vm.hostname = "slave1"
    m.vm.network "private_network", ip: "10.0.0.101"
    m.vm.provider "virtualbox" do |v|
      v.memory = 512
    end
  end

  config.vm.define "slave2" do |m|
    m.vm.box = "ubuntu/trusty64"
    m.vm.hostname = "slave2"
    m.vm.network "private_network", ip: "10.0.0.102"
    m.vm.provider "virtualbox" do |v|
      v.memory = 512
    end
  end

  config.vm.define "control" do |m|
    m.vm.box = "ubuntu/trusty64"
    m.vm.hostname = "control"
    m.vm.network "private_network", ip: "10.0.0.100"
    m.vm.provider "virtualbox" do |v|
      v.memory = 512
    end
    m.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y python-pip build-essential libssl-dev libffi-dev python-dev
      pip install ansible
    SHELL
  end

end
