# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure("2") do |config|
  
  config.vm.box = "jiatui/centos-7.6"
  config.vm.box_check_update = false

  config.vm.define "node1" do |node1|
    node1.vm.hostname = 'controller'

    node1.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 4096]
      v.customize ["modifyvm", :id, "--cpus", 1]
      v.customize ["modifyvm", :id, "--name", "controller"]
    end
    
    node1.vm.network "private_network", ip: "10.0.0.11"
    node1.vm.network "public_network", bridge: "enp0s31f6", ip: "192.168.100.228" 
    #node1.vm.network "forwarded_port", guest: 80, host: 8080
  end
#####node2#########
  config.vm.define "node2" do |node2|
    node2.vm.hostname = 'compute'

    node2.vm.provider :virtualbox do |m|
      m.customize ["modifyvm", :id, "--memory", 4096]
      m.customize ["modifyvm", :id, "--cpus", 2]
      m.customize ["modifyvm", :id, "--name", "compute"]
    end
    
    node2.vm.network "private_network", ip: "10.0.0.31"
    node2.vm.network "public_network", bridge: "enp0s31f6", ip: "192.168.100.229" 
    #node2.vm.network "forwarded_port", guest: 80, host: 8080
  end

######node3
  config.vm.define "node3" do |node3|
    node3.vm.hostname = 'node3'

    node3.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 4096]
      v.customize ["modifyvm", :id, "--cpus", 1]
      v.customize ["modifyvm", :id, "--name", "node3"]
    end
    
    node3.vm.network "private_network", ip: "10.0.0.14"
    node3.vm.network "public_network", bridge: "enp0s31f6", ip: "192.168.100.230" 
    #node3.vm.network "forwarded_port", guest: 80, host: 8080
  end


  #config.vm.network "forwarded_port", guest: 80, host: 8080
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  config.vm.synced_folder "/home/xuliang", "/vagrant_data"
 
  config.ssh.username="vagrant"
  config.ssh.password="vagrant"

  
end
