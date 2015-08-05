# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "centos-66-x64"
  config.vm.box_url = "https://github.com/tommy-muehle/puppet-vagrant-boxes/releases/download/1.0.0/centos-6.6-x86_64.box"
  config.vm.hostname = 'centos66.local'
  # rsync path
#   config.vm.synced_folder "","/home/vagrant/apps",type: "rsync",rsync_exclude:[".git"]
  config.vm.define :private_node do |node|
    config.vm.network "forwarded_port", guest: 80, host: 8080
    config.vm.network "private_network", ip: "192.168.33.10"
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provision_vagrant.yml"
    ansible.inventory_path = "hosts"
    ansible.limit = "all"
  end
end
