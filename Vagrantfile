# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "debian/jessie64"
  config.ssh.insert_key = true

  config.vm.provider :virtualbox do |v|
    v.name = "vagrantHostname"
    v.memory = 2048
    v.cpus = 1
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.hostname = "vagrantHostname"
  config.vm.network :private_network, ip: "192.168.69.69"

  # Set the name of the VM. See: http://stackoverflow.com/a/17864388/100134
  config.vm.define :vagrantHostname do |vagrantHostname|
  end

  # Ansible provisioner.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.inventory_path = "ansible/inventory"
    ansible.sudo = true
  end

end
