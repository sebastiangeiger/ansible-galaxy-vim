# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "geerlingguy/ubuntu2004"
  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |v|
    v.memory = 4096
    v.cpus = 2
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  # General Ansible VM
  config.vm.define "ubuntu" do |vm|
    vm.vm.network :private_network, ip: "192.168.6.7"

    vm.vm.provision :ansible do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "manual_tests/playbook.yml"
      ansible.inventory_path = "manual_tests/inventory"
      ansible.become = true
    end
  end

end
