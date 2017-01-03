# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id, "--memory", 1024]
  end
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 5050, host: 5050
  config.vm.network :private_network, ip: "192.168.10.10"
  config.vm.network :public_network, ip: "192.168.1.5", bridge: "enp3s0"
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
