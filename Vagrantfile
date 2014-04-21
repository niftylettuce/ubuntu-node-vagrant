# -*- mode: ruby -*-
# vi: set ft=ruby:

Vagrant.configure("2") do |config|

  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.provision :shell, :inline => "sudo -i -u vagrant /vagrant/vagrant/setup"

  # configure virtualbox shared folders for symlinking
  config.vm.provider :virtualbox do |vb|
    vb.customize [
      "modifyvm", :id,
      "--memory", "1024",
      "--name"  , "ubuntu-node-vagrant"
    ]
    vb.customize ["setextradata", :id, "VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root", "1"]
  end

  config.vm.network :public_network

  config.ssh.forward_agent = true


end
