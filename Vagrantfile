# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "ros-indigo-desktop-trusty64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  #config.vm.hostname = "ros-indigo-desktop-trusty64"

  #config.vm.share_folder("ardupilot", "/home/vagrant/ardupilot", ".")
  config.vm.share_folder "virtualenv", "/home/vagrant/rosws", "/Users/kp/dev/rosws"

  # Allow symlinks
  #config.vm.customize ["setextradata", :id, "VBoxInternal2/SharedFoldersEnableSymlinksCreate/cross-compiler", "1"]
  # Otherwise the compile will go into swap, making things slow
  config.vm.customize ["modifyvm", :id, "--memory", "2048"]

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "manifests"
    puppet.manifest_file  = "ros.pp"
    puppet.module_path = "modules"
  end

end

