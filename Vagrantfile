# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. 
Vagrant.configure("2") do |config|

  # The template to clone the VM from
   config.vm.box = "ubuntu/focal64"
  
  # Port Forward TCP Port 8080 on the Host to Port 80 on the VM
   config.vm.network "forwarded_port", guest: 80, host: 8080
  
  # Configure the provider (virtualbox) to set RAM and CPU to a specific amount
  config.vm.provider "virtualbox" do |vb|
  
   # Customize the amount of memory and CPU on the VM:
   vb.memory = "1024"
   vb.cpus = 2
  
  end
  
  # Have Vagrant provision the Virtual Machine...
  # Install LAMP stack software
  
   config.vm.provision "shell", inline: <<-SHELL
  
   apt-get update
   apt-get install -y apache2

   # add additional lines of code here to install: mysql and the php language packages
   apt-get install -y mariadb-server
   apt-get install -y php
   apt-get install -y libapache2-mod-php
   apt-get install -y php-mysql
   SHELL
  
  end