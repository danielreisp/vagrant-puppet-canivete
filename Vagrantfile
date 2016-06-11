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
  # puppetlabs/ubuntu-14.04-64-nocm - sem puppet
  # puppetlabs/centos-7.0-64-puppet - puppet 4.2
  # puppetlabs/centos-6.6-64-nocm
  # puppetlabs/centos-7.0-64-nocm - sem puppet
  config.vm.box = "puppetlabs/centos-6.6-64-nocm"
  # pastas que podem ser sincronizadas.
  #config.vm.synced_folder "/Users/daniel/repositorios/vagrant/" , disabled: true

  # especificando a versão do puppet de todas as VM
  config.puppet_install.puppet_version = "3.8.7"

  # Configurações genéricas do provedor virtualbox
  #config.vm.provider "virtualbox" do |v|
    # Linked clones are based on a master VM
  #  v.linked_clone = true
    # Customize the amount of memory on the VM:
  #  v.memory = "256"
#    v.cpus = 2
#  end
  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
   config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

    config.vm.define :canivete do |canivete_config|
      canivete_config.vm.hostname = "canivete.devops.br"
      canivete_config.vm.network  :private_network,
                            :ip => "192.168.33.10"

    #A list of valid versions can be found at: http://docs.puppetlabs.com/release_notes/
    canivete_config.puppet_install.puppet_version = "3.8.7"
    canivete_config.vm.provision "puppet" do |puppet|
      puppet.manifest_file = "init.pp"
    end
      canivete_config.vm.provider "virtualbox" do |v|
        # Linked clones are based on a master VM
        #v.linked_clone = true
        # Customize the amount of memory on the VM:
        v.memory = "256"
        v.cpus = 2
      end
    end
end
