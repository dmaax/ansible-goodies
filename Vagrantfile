# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # General Vagrant VM configuration.
  config.vm.box = "ubuntu/jammy64"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider :virtualbox do |v|
    v.memory = 1024
    v.linked_clone = true
  end

  # Vagrant main VM
  config.vm.define "ansible" do |app|
    app.vm.hostname = "ansible"
    app.vm.network :private_network, ip: "192.168.56.10"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbooks/lemp_stack.yml"
    ansible.compatibility_mode = "2.0"
    ansible.version = "2.16.4"
  end

end