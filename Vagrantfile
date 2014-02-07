# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "centos-6.5-x86_64"
  config.vm.box_url = "https://dl.dropboxusercontent.com/s/np39xdpw05wfmv4/centos-6.5-x86_64.box"

  config.vm.network :private_network, ip: "10.10.10.10"

  config.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777","fmode=777"]
  config.vm.synced_folder "/Users/edwin/software", "/software"


  config.vm.hostname = "vagrantcentos64"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--name", "vagrantcentos64"]
  end
  
  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "puppet/manifests"
    puppet.module_path = "puppet/modules"
    puppet.manifest_file  = "site.pp"
    puppet.options = "--verbose"
  end


end
