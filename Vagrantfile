# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box_version="2004.01"
  config.vm.box = "centos/7"

  # workaround ssh issue https://github.com/hashicorp/vagrant/issues/10601#issuecomment-653057929
  config.ssh.config = "empty_ssh_config"

  config.vm.box_check_update = false

  

  config.vm.provider "virtualbox" do |vb| 
    vb.memory = "2048"
    # vb.linked_clone = true
  end

  

  config.vm.define "sh1r1", primary: true do |sh1r1|
    sh1r1.vm.network "forwarded_port", guest: 8123, host: 8123
    sh1r1.vm.provision :shell, path: "bootstrap_centos.sh"
    sh1r1.vm.hostname = "sh1r1"
  end

  # config.vm.define "clear" do |db|

    
  # end
end
