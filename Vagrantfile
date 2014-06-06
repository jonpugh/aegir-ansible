# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.network "private_network", ip: "1.2.3.4"
  config.vm.network "public_network"
  config.vm.synced_folder "repos", "/repos"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.sudo = true
    ansible.extra_vars = { ansible_ssh_user: 'vagrant' }
  end

end
