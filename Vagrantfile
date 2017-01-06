# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define :web01 do |web01|
      web01.vm.box = "debian/jessie64"
      web01.ssh.insert_key = true
  end

  config.vm.synced_folder "src", "/var/www/html", type: "rsync",
    rsync__exclude: ".git/"

  config.vm.provider :virtualbox do |v|
    v.name = "web01"
    v.memory = 2048
    v.cpus = 1
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.hostname = "web01"
  config.vm.network :private_network, ip: "192.168.69.69"


  # Ansible provisioner.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.inventory_path = "ansible/inventory"
    ansible.sudo = true
  end

end
