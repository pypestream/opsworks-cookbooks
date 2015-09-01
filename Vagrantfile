# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu-trusty64"
  config.vm.box_url = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-14.04_chef-provisionerless.box"

  # Specifies the chef version Opsworks is running
  config.omnibus.chef_version = "11.10.0"

  config.vm.provision :chef_solo do |chef|
    chef.add_recipe "build-essential::default"
    chef.add_recipe "runit"
    chef.add_recipe "redisio"
    chef.add_recipe "redisio::enable"
  end
end


