# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
   config.vm.box_check_update = false

   config.vm.define :canivete_centos do |canivete_config|
      canivete_config.vm.box = "puppetlabs/centos-6.6-64-nocm"
      canivete_config.vm.hostname = "canivete-centos"
      canivete_config.vm.network  :private_network,
                                  :ip => "192.168.33.10"
      canivete_config.puppet_install.puppet_version = "3.8.5"

      canivete_config.vm.provision "puppet" do |puppet|
        puppet.manifest_file = "init.pp"
      end

      canivete_config.vm.provider "virtualbox" do |v|
        # Linked clones are based on a master VM
        v.linked_clone = false
        # Customize the amount of memory on the VM:
        v.memory = "256"
        v.cpus = 2
      end
    end # end   config.vm.define :canivete_centos do |canivete_config|




    config.vm.define :canivete_ubuntu do |canivete_config|
      canivete_config.vm.box = "puppetlabs/ubuntu-12.04-64-nocm"
      canivete_config.vm.hostname = "canivete-ubuntu"
      canivete_config.vm.network  :private_network,
                            :ip => "192.168.33.11"

    #A list of valid versions can be found at: http://docs.puppetlabs.com/release_notes/
    canivete_config.puppet_install.puppet_version = "3.8.5"
    canivete_config.vm.provision "puppet" do |puppet|
      puppet.manifest_file = "init.pp"
    end
      canivete_config.vm.provider "virtualbox" do |v|
        # Linked clones are based on a master VM
        v.linked_clone = false
        # Customize the amount of memory on the VM:
        v.memory = "256"
        v.cpus = 2
      end
    end
end
