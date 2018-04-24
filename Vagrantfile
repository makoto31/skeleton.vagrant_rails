# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "sample"

  config.vm.provider "virtualbox" do |vb|
    # 1GBメモリ割当
    vb.memory = "1024"
  end

  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.network :private_network, ip: "192.168.33.36"

  # 環境構築
  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "ansible.yml"
  end

end
