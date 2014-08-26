# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/precise32"

  config.vm.network :private_network, ip: "192.168.33.12"

  # config.vm.network :public_network
  # config.vm.synced_folder "../data", "/vagrant_data"
  # config.vm.synced_folder ".", "/vagrant", :nfs => true
  config.vm.synced_folder ".", "/vagrant", id: "vagrant-root", nfs: true

  config.ssh.private_key_path = ["~/.ssh/id_rsa", "~/.vagrant.d/insecure_private_key"]
  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--name", "vagrant12"]
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "provisioning/setup.yml"
    ansible.raw_arguments = "-i ansible_host"
    #ansible.inventory_file = "provisioning/ansible_host"
    #ansible.verbose = "vvvv"
  end

end
