# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.box = "bento/ubuntu-20.04-arm64"

  config.vm.provider "vmware_desktop" do |vmware|
      vmware.cpus = 2
      vmware.memory = 2048
      vmware.gui = true
  end

  config.vm.network "forwarded_port" , guest: 80, host: 8080

  config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yaml"
      ansible.inventory_path = "inventory.ini"
  end

end
