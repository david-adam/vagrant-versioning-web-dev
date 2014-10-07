# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hashicorp/precise32"
  config.vm.hostname = "web-dev"

  config.vm.provision "shell", path: "provision.sh"
  config.vm.network "forwarded_port", guest: 80, host: 8088, id: "nginx", auto_correct: true

  config.vm.synced_folder "./", "/vagrant", disabled: true
  config.vm.synced_folder "www", "/vagrant/www"
  config.vm.synced_folder "sites-enabled", "/vagrant/sites-enabled"
end
