# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/#{config.vm.box}.box"

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    #chef.roles_path = "roles"
    
    chef.add_recipe "apt"

    chef.add_recipe "erlang"
    chef.add_recipe "chicagoboss"

    chef.add_recipe "docker"
  
    chef.json = {
      :erlang => {
        :install_method => "source",
        :source => {
          :version => "R15B01"
        }
      }
    }
  end
end
